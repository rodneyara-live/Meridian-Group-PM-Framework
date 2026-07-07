---
type: workflow
code: WF-008
tags: [workflow, github, sync]
updated: 2026-04-19
---
# WF-008 — Sync Individual GitHub Repos

> **Only under explicit PM invocation.**
>
> **Invocation:** PM runs `_Vault/scripts/github_sync.py --vault [path]` → Claude processes the resulting JSON in `Transcripciones-WIP/`.

> ⚠️ Claude never runs the script on its own initiative. It only processes the JSON when the PM requests it.

---

## Identify the file type in `Transcripciones-WIP/`

| File suffix | Origin | Flow |
|---|---|---|
| `-github.json` | `_Vault/scripts/github_sync.py` → GitHub API | This WF (WF-008) |
| `.txt`, `.md`, `.vtt`, etc. | Meeting transcription | [[WF-001-process-minutes-transcription]] |

---

## Identity mechanism — new or existing repo?

Search all `Logbook.md` in the vault for the field `github-repo: [repo-name]`. This field, together with `origen: innovacion-github`, is the permanent identifier. **Never modify these two fields once set.**

---

## Branch A — New repo (no entry in the vault)

Detected because no `Logbook.md` has `github-repo: [repo-name]`.

1. Present the PM with a repo summary (description + first lines of the README) and ask:
   - What will it be called in the vault? (convention: `IE-[PE]-[OE]-[IE]_Name` or `PR-7-[NN]_Name`)
   - Which Strategic Initiative from [[Matriz-Estrategica-2026]] does it align with?
2. With PM confirmation, create the standard structure:
   - Folder `Projects/[Code]_[Name]/` with subfolders `Minutes/`, `Transcripciones/`, `Documents/`
   - Initial status `README.md`
   - `Logbook.md` with first entry (headline: `Onboarding from GitHub — [repo-name]`) and fields `github-repo`, `origen`, `github-last-sync` in the frontmatter
3. Optionally (ask the PM): generate `FOR-002` project charter and `FOR-003` preliminary requirements matrix based on the repo README.
4. Update `Projects/README.md` and `Matriz-Estrategica-2026` (see START-HERE — Integrity rules steps 5 and 6).
5. Move the JSON to `Projects/[Code]/Transcripciones/` upon onboarding completion. While onboarding is not complete, the file stays in `Transcripciones-WIP/`.

---

## Branch B — Existing repo (already has entry in the vault)

Detected because a `Logbook.md` exists with `github-repo: [repo-name]`.

1. Generate a **GitHub Report** in `Projects/[Code]/Minutes/` named:
   ```
   YYYY-MM-DD_GitHub-Report-[repo-name].md
   ```
   The prefix `GitHub-Report-` distinguishes these reports from meeting minutes.

2. The report includes:
   - Activity summary since last sync (compare with `github-last-sync` from the Logbook)
   - Relevant commits: message + author + date
   - Open issues — each issue becomes an actionable with full tags:
     ```
     - [ ] [[Sponsor]]: [issue title] — GitHub #[number] 📅 YYYY-MM-DD #IE-X-X-X #resp/Name-Lastname #action
     ```

3. Update the project's `Logbook.md`:
   - `github-last-sync`: current sync date
   - `last_event`: one-sentence summary of detected activity (max ~120 chars)
   - `status` and `completion`: update if activity justifies it
   - `## 📌 Current Status` section: update with sync summary
   - New entry in `## History` referencing the report

> If there is a project meeting in the same period, document it with standard WF-001. The GitHub Report is complementary — it does not replace meeting minutes.

---

## Last step — Commit and push

```bash
cd "/path/to/vault/Meridian-Group-Projects-Vault"
git add -A
git commit -m "feat([code]): sync GitHub [repo-name] + logbook"
git push
```
