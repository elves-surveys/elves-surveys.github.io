# ELVES Surveys Website

Public website for the ELVES family of astronomical surveys, built with [Astro](https://astro.build) and deployed to GitHub Pages.

**Live site:** https://elves-surveys.github.io

## Surveys

| Survey | Description |
|---|---|
| [ELVES](https://elves-surveys.github.io/elves/) | Satellites of Milky Way-mass hosts in the Local Volume |
| [ELVES-Dwarf](https://elves-surveys.github.io/elves-dwarf/) | Satellites of dwarf hosts in the Local Volume |
| [ELVES-Field](https://elves-surveys.github.io/elves-field/) | Dwarf galaxies in the Local Volume field |

## Development

**Prerequisites:** Node.js 18+

```bash
npm install
npm run dev       # start dev server at http://localhost:4321
npm run build     # build static site to dist/
npm run preview   # preview the built site locally
```

## Project Structure

```
src/
  content/        # structured data (JSON)
    surveys.json
    papers.json
    data-products.json
    team.json
  pages/          # routes
    index.astro         # home page (/)
    [slug]/index.astro  # survey pages (/elves/, /elves-dwarf/, /elves-field/)
    team/index.astro    # team page (/team/)
  components/     # reusable Astro components
  layouts/        # page layout wrapper
  styles/         # global CSS with design tokens
```

## Updating Content

All site content lives in `src/content/` as JSON files — no code changes needed for routine updates.

- **Survey descriptions** → `src/content/surveys.json`
- **Papers** → `src/content/papers.json`
- **Data products / download links** → `src/content/data-products.json`
- **Team members** → `src/content/team.json`

## Deployment

The site deploys automatically to GitHub Pages via GitHub Actions on every push to `main`. The workflow is defined in [.github/workflows/deploy.yml](.github/workflows/deploy.yml).

To deploy manually:

```bash
npm run build
# push the dist/ output, or let the workflow handle it
```

## Design

Minimal academic style inspired by Apple.com: white background, clean sans-serif typography, generous whitespace, subtle gray borders, one restrained accent color. Heavy animations and complex UI are intentionally avoided to keep the site fast, accessible, and easy to maintain long-term.
