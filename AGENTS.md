# Repository Guidelines

## Project Structure & Module Organization
- Root contains two standalone calculators: `index.html` (Amvuttra model) and `setidegrasib.html` (Setidegrasib model).
- Each HTML file is self-contained (markup, styling, and JavaScript in one file); there is no separate `src/`, build pipeline, or package manager config.
- `README.md` is currently minimal; use clear in-file labels/headings in each calculator for user-facing assumptions and model notes.
- Keep shared UX patterns aligned across both pages (summary cards, assumptions section, forecast table behavior).

## Build, Test, and Development Commands
- No compile step is required; open files directly in a browser for quick checks.
- Recommended local server for stable testing:
  - `python -m http.server 8000`
  - Visit `http://localhost:8000/` for `index.html` and `/setidegrasib.html` for the second model.
- Optional formatting/linting can be done manually (no repository-standard tool is configured yet).

## Coding Style & Naming Conventions
- Use semantic HTML and keep accessibility attributes (`aria-*`, labels, roles) intact.
- Match existing style: 2-space indentation in HTML/CSS/JS blocks, descriptive IDs/classes, and camelCase for JavaScript variables/functions.
- Prefer explicit, domain-meaningful names (for example, `discountRate`, `cashFlowAtYear`) over short abbreviations.
- When adding calculations, keep constants and assumptions easy to find and edit.

## Testing Guidelines
- There is no automated test suite in this repository today.
- Validate changes with manual smoke tests in both calculators:
  - edit key assumptions,
  - confirm table recalculation,
  - verify NPV and risk-adjusted NPV updates,
  - check tab/section behavior and basic accessibility labels.
- If adding tests in the future, place them in a top-level `tests/` directory and document run instructions in `README.md`.

## Commit & Pull Request Guidelines
- Follow existing commit style: short, imperative summaries (for example, `Fix patient forecast recalculation`, `Extend Amvuttra forecast through 2036 patent expiry`).
- Keep commits scoped to one logical change (calculation fix, assumptions update, or UI behavior tweak).
- PRs should include:
  - purpose and business/modeling impact,
  - files changed,
  - manual validation steps,
  - screenshots or short recordings for UI changes.

## Security & Configuration Tips
- Do not commit sensitive internal assumptions, credentials, or non-public source data.
- Keep external references (e.g., regulatory or filing links) reputable and clearly labeled as assumptions vs. verified facts.
