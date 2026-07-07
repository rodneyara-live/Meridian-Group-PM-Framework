---
type: workflow
code: WF-013
tags: [workflow, report, portfolio, html, management]
updated: 2026-05-20
---
# WF-013 — Tactical Early Bird HTML Executive Report

> **Invocation:** *"Generate the Early Bird for [name]"* · *"Give me the portfolio HTML report"* · *"Update the portfolio executive report"* · *"Prepare the Early Bird to share with management"*
>
> **Output:** `Tactical-Early-Bird-YYYY-MM-DD.html` at the vault root
> **Required inputs:** none — reads directly from the vault's `Logbook.md` files

> ℹ️ This flow generates a self-contained HTML ready to share with executives who do not have access to Obsidian. The `Dashboard-Madrugador-Tactico.md` dashboard remains the living source for internal use; this report is the exportable version.

---

## Step 1 — Determine the date

Get the current system date:

```bash
date +%Y-%m-%d
```

Use it as `DATE` in the output filename.

---

## Step 2 — Run the script

The script reads all `Logbook.md` files from the vault and generates the HTML. It is located at `_Vault/scripts/generar_reporte_html.py`.

```bash
python3 "/path/to/vault/Meridian-Group-Projects-Vault/_Vault/scripts/generar_reporte_html.py" \
  --vault "/path/to/vault/Meridian-Group-Projects-Vault" \
  --output "/path/to/vault/Meridian-Group-Projects-Vault/Tactical-Early-Bird-DATE.html"
```

Replace `DATE` with the date obtained in Step 1 (e.g., `2026-05-20`).

If it fails due to missing dependencies: `pip install pyyaml --break-system-packages`

---

## Step 3 — Verify and deliver

Confirm that the file exists and is larger than 50 KB. Then share the link:

```
[View Tactical Early Bird — DATE](computer:///path/to/vault/Meridian-Group-Projects-Vault/Tactical-Early-Bird-DATE.html)
```

---

## What the report includes

- **Fixed sidebar** with section navigation and health traffic light (stays visible while scrolling)
- **Summary cards** with project count by status and traffic light distribution
- **Tables by section:** In Progress · Completed / Showcased · Not Started · Paused · To Be Defined
- **Each row:** code, priority, name, company (color tags), latest logbook status, progress bar, Δ days, planned and revised dates
- **Meridian Group corporate design:** colors #0081C1 · #FF7100 · #00AA55 · #FFD02A

**Rules applied automatically by the script:**
- Only `C1` and `C2` projects (excludes `C3`)
- Showcased projects → 100% completion
- Health: Green ≤5% deviation · Yellow 5–15% · Red >15% over base duration

---

## Notes

- The generated HTML file is self-contained (no external dependencies) — can be emailed or opened in any browser.
- It does not modify any `Logbook.md` or any vault file. It is a read-only + generation operation.
- If the portfolio has changed since the last report, simply invoke again — the script always reads the current state.

---

## Commit and push

```bash
cd "/path/to/vault/Meridian-Group-Projects-Vault"
git add -A
git commit -m "docs(portfolio): HTML Early Bird report YYYY-MM-DD"
git push
```

---

## References

- `_Vault/scripts/generar_reporte_html.py` — generation script
- [[Dashboards/Dashboard-Madrugador-Tactico]] — live dashboard for internal use
- [[WF-006-weekly-executive-summary|WF-006]] — weekly executive summary in Markdown (alternative)
