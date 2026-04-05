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
| `sdd-learning` | Domain context for this repo — topic folders, SDD focus, zero-copy, voice |
| `topic-units` | On-demand topic layout, `NN_<slug>.md` naming, governance checks |
| `ci-checks` | Local commands aligned with `.github/workflows/ci-documentation.yml` (and agent-docs lint job) |
| `docs-verification` | Structure, naming, and link sanity vs `README.md` / `CLAUDE.md` / rule `09` |
| `workspace-review` | Full audit checklist for this Markdown learning workspace |
| `e2e-testing` | Smoke checks — markdownlint (+ optional Lychee) |

**Note:** The live skills for automation and agents are the mirrored trees at the repo root (this folder and `.cursor/skills/`).
