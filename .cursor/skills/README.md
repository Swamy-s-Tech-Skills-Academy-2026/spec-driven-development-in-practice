# Agent skills (canonical)

This directory is the **source of truth** for bundled agent skills used with Cursor and GitHub Copilot (see `.github/copilot-instructions.md`).

## Mirror

`.cursor/skills/` must stay **identical** to `.github/skills/` (same paths, same `SKILL.md` and `README.md` bytes). After editing here, copy the updated tree to `.cursor/skills/`.

### Verify parity (PowerShell, repo root)

```powershell
$gRoot = Join-Path (Get-Location) ".github\skills"
$cRoot = Join-Path (Get-Location) ".cursor\skills"
Get-ChildItem $gRoot -Recurse -Filter SKILL.md | ForEach-Object {
 $rel = $_.FullName.Substring($gRoot.Length + 1)
 $c = Join-Path $cRoot $rel
 if (-not (Test-Path $c)) { Write-Host "Missing in .cursor/skills: $rel"; return }
 if ((Get-FileHash $_.FullName -Algorithm SHA256).Hash -ne (Get-FileHash $c -Algorithm SHA256).Hash) {
 Write-Host "MISMATCH: $rel"
 }
}
Get-ChildItem $cRoot -Recurse -Filter SKILL.md | ForEach-Object {
 $rel = $_.FullName.Substring($cRoot.Length + 1)
 $g = Join-Path $gRoot $rel
 if (-not (Test-Path $g)) { Write-Host "Extra in .cursor/skills (not in .github): $rel" }
}
```

## Bundled skills

| Folder | Purpose |
|--------|---------|
| `data-preprocessing` | Domain context — this repo (seven layers incl. discussion-prompts + assignments; weeks on demand) |
| `week-companions` | Seven-layer week parity, migration SOP, definition of done, tracker (append rows as weeks start) |
| `ci-checks` | Local commands aligned with `.github/workflows/ci-*.yml` |
| `docs-verification` | Companion links, layout, and naming vs `docs/01_repository-structure.md` |
| `workspace-review` | Full audit checklist for this educational repo |
| `e2e-testing` | Smoke checks (env, notebook parse, optional manual notebook run) |

**Note:** Skills that lived only under `source-material/.github/skills` or `source-material/.cursor/skills` are **staging copies**. The live skills for automation and agents are **only** the mirrored trees at the repo root (this folder and `.cursor/skills/`).
