# Repository Guidelines

## Project Structure & Module Organization
Content lives in `index.md` with reusable blocks from `_includes/`, while `_layouts/homepage.html` defines the page shell. Structured data such as publications sits in `_data/publications.yml`, styles reside in `_sass/`, and static assets (images, downloads) belong in `assets/`. Keep the pre-rendered HTML offline variant in `html_source_file/` synced only when you regenerate export-ready pages.

## Build, Test, and Development Commands
Run `bundle install` once to pull required gems. Use `bundle exec jekyll serve --livereload` during edits to rebuild the site locally on <http://localhost:4000>. Before opening a pull request, run `bundle exec jekyll build` to ensure `_site/` generates cleanly. If you suspect outdated configuration, `bundle exec jekyll doctor` highlights deprecated settings.

## Coding Style & Naming Conventions
Follow existing YAML front matter with `---` fences and two-space indentation. Markdown files favor sentence-case headings and concise lists. Liquid tags should stay on their own lines for readability. In `_sass/`, keep declarations grouped and indented two spaces; favor lowercase, hyphenated class names. Place new images under `assets/img/` using descriptive filenames such as `project-detection-2024.png`.

## Testing Guidelines
There is no automated test suite, so rely on the Jekyll build pipeline. After content or data changes, run `bundle exec jekyll build --trace` to surface Liquid or YAML errors. Review the served site across light and dark mode via `bundle exec jekyll serve` and spot-check generated `_site/` markup before deploying.

## Commit & Pull Request Guidelines
Commit messages typically use imperative verbs with brief context (e.g., `Add academic profile report`, `Update publications data`). Keep related changes together and avoid bundling content edits with style overhauls. Pull requests should include: a summary of what changed, impacted sections or data files, any manual verification steps, and screenshots or GIFs when visual layout shifts.

## Content & Localization Notes
When updating textual content, verify language consistency across `README.md` variants if the change affects general project instructions. Data-driven sections (such as publications) should stay sorted chronologically, and each entry should supply all keys used by the templates to avoid runtime warnings.
