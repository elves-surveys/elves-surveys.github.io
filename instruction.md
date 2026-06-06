# CLAUDE.md

## Project overview

This repository hosts the public website for the ELVES family of surveys:

1. **ELVES**: satellites of Milky Way-mass hosts in the Local Volume.
2. **ELVES-Dwarf**: satellites of dwarf hosts in the Local Volume.
3. **ELVES-Field**: dwarf galaxies in the Local Volume field.

The website should provide a clean public-facing portal for papers, survey descriptions, figures, and especially data products. The preferred URL structure is:

- `/elves/`
- `/elves-dwarf/`
- `/elves-field/`

The site should be suitable for an academic survey data release. It should be visually minimal, modern, and stable. The intended aesthetic is “Apple-like”: clean typography, generous whitespace, subtle hierarchy, restrained colors, and polished cards/tables.

## Primary goals

The website should make it easy for visitors to:

- Understand the scientific scope of the three surveys.
- Find published papers associated with each survey.
- Download data products (mainly fits files and/or CSV tables).
- See what each data product contains.
- Visualize the dwarf galaxies in these surveys (including showing their images, and manipulate with their properties)
- Show example notebooks on how to interpret the data (e.g., reproduce the figures in published papers)
- Cite the appropriate papers when using the data.
- Contact the survey team (by listing main author's contacts).

## Design principles

Use a minimal, clean, academic style.

Prioritize:

- Readability.
- Clear navigation.
- Stable URLs.
- Fast loading.
- Accessibility.
- Mobile responsiveness.
- Easy future maintenance.

Avoid:

- Heavy animations.
- Overly complex UI.
- Excessive color.
- Dark, cluttered layouts.
- Framework-specific complexity unless needed.
- Fancy interactions that obscure data access.

## Visual style

Use an understated Apple-inspired design:

- White or near-white background.
- Large, confident headings.
- Generous spacing.
- Clean sans-serif typography, but the text should be seen very easily.
- Subtle gray borders.
- Rounded cards.
- Soft shadows only when useful.
- One restrained accent color.
- Responsive grid layout.


## Content model

Keep survey information, papers, and data products in structured files when possible.

Suggested files:

- `src/content/surveys.yml`
- `src/content/papers.yml`
- `src/content/data-products.yml`

Each survey page should be generated from structured metadata where possible.

## Required pages

### Home page: `/`

The home page should introduce the ELVES survey family and provide three prominent survey cards:

- ELVES
- ELVES-Dwarf
- ELVES-Field

Each card should include:

- A one-sentence description.
- Host galaxy type.
- Approximate distance regime.
- Link to the survey page.
- Link to data products if available.

The home page should also include:

- A short “Data releases” section.
- A “Papers” section with recent or key publications.
- A citation/contact section.

### ELVES page: `/elves/`

This page should include:

- Survey overview.
- Science motivation.
- Main published papers.
- Data products section.
- Recommended citation.
- Download table.
- Contact information.

### ELVES-Dwarf page: `/elves-dwarf/`

This page should include:

- Survey overview.
- Dwarf-host satellite science motivation.
- Main published papers.
- Data products section.
- Recommended citation.
- Download table.
- Contact information.

### ELVES-Field page: `/elves-field/`

This page should include:

- Survey overview.
- Field dwarf science motivation.
- Main published papers.
- Data products section.
- Recommended citation.
- Download table.
- Contact information.

## Data-products interface

Data products are the most important part of the website.

Each survey page should have a clear data-products section with a table or card list containing:

- Product name.
- Version.
- Release date.
- Short description.
- File type.
- Approximate file size, if known.
- Download link.
- Documentation link, if applicable.
- Recommended citation.

For example:

| Product | Version | Description | Format | Download |
|---|---:|---|---|---|
| Host catalog | v1.0 | Properties of target host galaxies | CSV/FITS | Download |
| Satellite catalog | v1.0 | Confirmed and candidate satellites | CSV/FITS | Download |
| Image cutouts | v1.0 | Survey imaging cutouts | FITS/PNG | Download |
| Host search coverage | v1.0 | Search coverage maps | CSV | Download |
| Completeness curves | v1.0 | Detection completeness products | CSV | Download |

The table should be readable on mobile. If tables are too wide, use stacked cards on narrow screens.

## Paper entries

Each paper entry should contain:

- Title.
- Authors.
- Year.
- Journal/status.
- Short description.
- ADS link.
- arXiv link.
- DOI link, if available.
- Related survey/surveys.
- Recommended citation note.

Do not invent bibliographic details. Use placeholders when details are unknown.

## Citation section

Each survey page should include a citation block such as:

> If you use data products from this survey, please cite [paper placeholder] and acknowledge the ELVES survey.

Use placeholders until the final citation text is provided.

## Implementation preferences

Preferred implementation:

- Static site.
- GitHub Pages compatible.
- Minimal dependencies.
- Easy to update by editing YAML/JSON/Markdown.
- Use semantic HTML.
- Use CSS variables for colors, spacing, and typography.
- Use responsive layout.
- Use accessible links and buttons.

Astro is preferred, but another static-site framework is acceptable if justified.

## Code style

- Keep components small and readable.
- Avoid premature abstraction.
- Avoid unnecessary JavaScript.
- Use descriptive class names.
- Keep global design tokens in one CSS file.
- Use structured content files for survey metadata.
- Do not hard-code large tables directly in page templates if the content can live in YAML/JSON.

## Scientific-content style

Use precise, professional academic language. Avoid hype.

Preferred tone:

- Clear.
- Formal.
- Concise.
- Suitable for an astronomical survey website.
- Written for both professional astronomers and advanced students.

Avoid phrases like:

- “Revolutionary”
- “Game-changing”
- “Unprecedented” unless explicitly supported
- “Beautiful data”
- “Amazing discoveries”

## Placeholder policy

Use clear placeholders for missing information, for example:

- `[ADS link pending]`
- `[DOI pending]`
- `[Data release v1.0 pending]`
- `[Citation text pending]`

Do not fabricate:

- Paper titles.
- Author lists.
- DOI links.
- Dataset filenames.
- Release dates.
- File sizes.

## Accessibility requirements

- Use semantic headings in order.
- Ensure sufficient color contrast.
- All links should be descriptive.
- Buttons should be keyboard accessible.
- Images should have meaningful alt text.
- Do not rely only on color to convey meaning.

## Deployment

The final site should be deployable through GitHub Pages.

If using Astro, configure the base path and output correctly for:

`https://elves-surveys.github.io/`

The desired public paths are:

- `https://elves-surveys.github.io/elves/`
- `https://elves-surveys.github.io/elves-dwarf/`
- `https://elves-surveys.github.io/elves-field/`

Include a GitHub Actions workflow for automatic deployment from the main branch.

## Important

Before making large structural changes, prefer a simple static implementation that is easy for astronomers to maintain. The website should serve the data products reliably for years.