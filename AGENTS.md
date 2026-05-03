# OpenCode Instructions: kraskura.github.io

This repository contains a Quarto-based academic portfolio/lab website deployed via GitHub Pages.

## Build and Deploy Workflow

- **Dev server:** Run `quarto preview` to run a local dev server with hot reload.
- **Build site:** Run `quarto render` to build the static site.
- **Ignore config:** `AGENTS.md` is excluded from the site build via the `project: render:` block in `_quarto.yml`. Ensure any future agent or instruction markdown files are excluded there so they don't appear on the live website.
- **Deployment:** GitHub Pages is configured to serve the `docs/` folder from the `main` branch. After rendering the site, you must **commit and push the generated `docs/` folder** alongside the source file changes. There is no automated CI pipeline.
- **Never edit `docs/` directly:** This directory is the generated `output-dir` configured in `_quarto.yml` and will be overwritten on the next render.

## Content Architecture

Avoid editing the top-level `.qmd` files directly for listing pages. Instead, update their data sources:

- **Team members (`people.qmd`)**: Add or edit entries in the `People/` directory (e.g., `people-pi.yml` or `people-graduate-students.yml`). These use custom EJS templates located in `ejs/`.
- **Projects (`projects.qmd`)**: Add or edit entries in the `Projects/` directory (e.g., `projects-fish.yml`, `projects-crayfish.yml`).
- **Lab Activities / Stories (`stories.qmd`)**: Create or edit `.qmd` markdown posts in the `Posts/` directory.
- **Publications (`publications.qmd`)**: This file *is* manually managed. Edit `publications.qmd` directly to add new papers.

## Styling and Configuration

- **Configuration:** Global layout and theme settings are in `_quarto.yml` and `_brand.yml`.
- **Custom CSS:** Found in `styles/styles.scss`.
- **Assets:** Images, banners, and logos are stored in `media/`.
