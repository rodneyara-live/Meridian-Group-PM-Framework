# Workflows — Operational Instructions for Claude

This folder contains the **Workflows (WF-NNN)** of the Meridian Group vault — operational instructions written for Claude. They define how Claude executes vault flows: processing transcripts, creating and updating logs, generating FORs, syncing repos, and verifying integrity.

> **SOPs for humans:** Standard Operating Procedures live in the sibling folder `[[Processes/README|Processes/]]`.

Claude reads the corresponding **WF** file **before executing** each task. WFs are the procedural source of truth — the invariant rules (WikiLinks, codes, tags, traffic lights, integrity) live in [[START-HERE]].

---

## Workflow Index

| Code | Name | When to Read |
|---|---|---|
| [[WF-001-process-minutes-transcription\|WF-001]] | Process Transcription → Minutes | Before processing any transcription |
| [[WF-002-logbook-and-FORs\|WF-002]] | Logbook and FORs (FOR-015, FOR-007) | Before creating/updating Logbook or generating any FOR |
| [[WF-006-weekly-executive-summary\|WF-006]] | Weekly Portfolio Executive Summary | Before preparing the Tactical Early Bird summary |
| [[WF-008-github-sync\|WF-008]] | Sync Individual GitHub Repos | Before processing a `-github.json` (backup, explicit invocation) |
| [[WF-009-vault-integrity\|WF-009]] | Verify Vault Integrity | Before auditing projects or preparing the Tactical |
| [[WF-014-teams-transcript-autofetch\|WF-014]] | Auto-download Teams Transcripts | Before configuring or running the `Get-TeamsTranscripts.ps1` script on the Windows VM |

---

## Note on Numbering

WF numbers correspond to the original workflows in the vault. Some numbers have no dedicated file because their flows were collapsed into broader WFs:

- **WF-003** (create Logbook) → included in WF-002
- **WF-004** (FOR-007) → included in WF-002
- **WF-005** (Operational Backlog) → inline in START-HERE (too short for its own WF)
- **WF-007** (update Dashboards) → inline in START-HERE (trivial: "edit the Logbook, not the dashboards")
- **WF-010** (Sync Innovation Hub) → retired 2026-07-07. The Innovation team and its projects are no longer an operational source for the vault; already-synced logs are preserved as historical record.
- **WF-011 to WF-013** → See START-HERE (messages, queries, HTML report)
- **WF-014** → New: auto-download Teams transcripts via Graph API
