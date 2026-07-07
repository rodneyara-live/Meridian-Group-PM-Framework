---
type: workflow
code: WF-014
tags: [workflow, teams, transcripts, vtt, graph-api, python]
updated: 2026-06-29
---
# WF-014 — Auto-download Teams Transcripts via Graph API

> **Purpose:** Eliminate manual VTT file downloads from Microsoft Teams.
> The `get_teams_transcripts.py` script runs on the Windows VM, queries recent meetings
> via Microsoft Graph API (device code flow), and deposits new VTT files into
> `Transcripciones-WIP/` for processing with [[WF-001-process-minutes-transcription]].
>
> Uses **Python + MSAL** (not PowerShell), so there are no execution policy or IT
> script restrictions.

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│  Windows VM (Meridian Group Microsoft Ecosystem)                     │
│                                                                 │
│  Microsoft Teams ─► Graph API ─► get_teams_transcripts.py      │
│                                       │                        │
│                                       ▼                        │
│                              Transcripciones-WIP/               │
│                                       │                        │
└───────────────────────────────────────┼────────────────────────┘
                                        │ Syncthing
                                        ▼
┌─────────────────────────────────────────────────────────────────┐
│  Linux (this machine)                                           │
│                                                                 │
│  Transcripciones-WIP/ ─► Claude detects new VTT ─► WF-001      │
└─────────────────────────────────────────────────────────────────┘
```

The vault is synced bidirectionally between Linux and Windows via Syncthing.
VTT files written by the script to `Transcripciones-WIP/` from Windows appear
automatically on Linux.

---

## Setup — Windows VM (one-time)

### 1. Install Python

Download from https://python.org (Python 3.12+). During installation,
**check "Add Python to PATH"**.

Verify in CMD or PowerShell:

```batch
python --version
```

### 2. Install dependencies

```batch
pip install msal requests python-dateutil
```

### 3. The script

Already in the vault (cloned via Syncthing on the Windows VM):

```
C:\...\Meridian Group-Projects-Vault\_Vault\scripts\get_teams_transcripts.py
```

No configuration needed. The first run will start the authentication flow.

---

## How to run

### Step 1 — On the Windows VM, open CMD and navigate

```batch
cd C:\path\Meridian Group-Projects-Vault\_Vault\scripts\
```

### Step 2 — Execute

```batch
python get_teams_transcripts.py
```

### Step 3 — Authenticate (first time only)

The script displays a code. In **any browser** (on the VM, your phone,
on Linux) open https://microsoft.com/devicelogin and enter the code.
Use your Meridian Group corporate account. No Azure AD needed.

### Step 4 — Advanced options

```batch
python get_teams_transcripts.py --days-back 14
python get_teams_transcripts.py --output-dir "D:\VTT"
python get_teams_transcripts.py --client-id "your-client-id"
```

---

## What the script does

1. **Authenticates** via device code flow (MSAL) — does not open a browser on the VM
2. **Searches** for meetings where you were organizer from `[today - DaysBack]`
3. **Queries** if transcripts are available via Graph API
4. **Downloads** new VTT files to `Transcripciones-WIP/` named `YYYYMMDD-Subject.vtt`
5. **Avoids duplicates** with a JSON log (`transcript-log.json`)
6. **Re-authenticates** silently on subsequent runs (cached token)

---

## Troubleshooting

### "pip is not recognized"

Python is not in PATH. Reinstall Python with "Add Python to PATH" checked,
or run `py -m pip install msal requests python-dateutil`.

### "No meetings found"

- Increase: `--days-back 14`
- Teams only exposes meetings where you were organizer
- The Graph API filter searches by `startDateTime` — applies from the most
  recent date backward

### "Access denied / 403 Forbidden"

The `OnlineMeetings.Read` permission requires the Meridian Group tenant to allow
user auto-consent. If it does not:

1. Go to https://entra.microsoft.com → App registrations → New
2. Name: `Teams-Transcript-Fetcher`, type: `Accounts in this directory`
3. Redirect URI: `Public client/native` → `https://login.microsoftonline.com/common/oauth2/nativeclient`
4. API Permissions → Add → Microsoft Graph → Delegated → `OnlineMeetings.Read`, `User.Read`
5. Copy the **Client ID** and run:
   ```batch
   python get_teams_transcripts.py --client-id "the-client-id"
   ```
6. If the tenant requires **admin consent**, ask IT to grant the permissions.

### "Token expired / session expired"

The token renews automatically (refresh token) for up to 90 days.
If it fails, delete the `msal_token_cache.bin` folder next to the script and run again.

---

## Integration with the vault

- **WF-001:** VTT files in `Transcripciones-WIP/` are processed with the normal flow
- **transcript-log.json:** Ignored in `.gitignore` (local machine artifact)
- **Script:** Both formats coexist — PowerShell (`.ps1`) and Python (`.py`)

---

## Last step — Commit

Downloaded and processed VTT files are committed as part of the normal session
closing (WF-001 final step). The `transcript-log.json` is not committed.
