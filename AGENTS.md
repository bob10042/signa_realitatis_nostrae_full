# Repository Guidelines

## Project Structure & Module Organization
The repository's source of truth is `signa_realitatis_nostrae_full.txt`. The rendered site lives in `docs/index.html`, while `signa_realitatis_nostrae_full.html` mirrors the latest export at the repository root. Keep archival assets in `docs/` so GitHub Pages serves them automatically.

## Build, Test, and Development Commands
- `pandoc signa_realitatis_nostrae_full.txt -o signa_realitatis_nostrae_full.html`: regenerate the standalone HTML from the master text.
- `Copy-Item signa_realitatis_nostrae_full.html docs/index.html`: refresh the GitHub Pages artifact after rebuilding.
- `Get-Content signa_realitatis_nostrae_full.txt -TotalCount 40`: spot-check the intro for formatting regressions.

## Coding Style & Naming Conventions
Write prose in the existing scholarly tone, preserving any Latin diacritics already present. Keep line length near 80-100 characters so diffs stay readable. When editing HTML, mirror the minimal structure in `signa_realitatis_nostrae_full.html` and prefer semantic tags over inline styling.

## Testing Guidelines
After regenerating HTML, open `docs/index.html` in a browser to confirm typography and anchor targets. Use `Test-Path docs/index.html` and `Get-FileHash docs/index.html` to verify the file updated as expected. When editing the text file, review the diff carefully to catch stray whitespace or encoding changes before committing.

## Commit & Pull Request Guidelines
Commits use the imperative mood (for example, `Add docs site for GitHub Pages`). Group related edits so content and generated artifacts can be reviewed separately. Pull requests should summarize the thematic change, list affected sections, and link any tracking issue or discussion. Include before-and-after screenshots when HTML layout or styling changes.

## Docs Publishing
GitHub Pages serves from `docs/`. After merging to the default branch, confirm the latest timestamp in `docs/index.html`. If the site does not refresh, trigger a rebuild from the Pages settings or push a no-op commit that touches the docs directory.
