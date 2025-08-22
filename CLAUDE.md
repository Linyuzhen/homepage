# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Local Development
```bash
# Install dependencies
bundle install
bundle add webrick

# Serve locally (default port 4000)
bundle exec jekyll server

# View at: http://localhost:4000
```

### Publishing
This site uses GitHub Pages with remote theme deployment. Changes to `main` branch are automatically deployed.

## Architecture Overview

This is a Jekyll-based academic homepage using the "minimal-light" theme as a remote theme. The site architecture follows Jekyll conventions with a focus on publications and academic content:

### Key Configuration
- **Remote Theme**: `yaoyao-liu/minimal-light` (defined in `_config.yml:45`)
- **Layout**: Single `homepage.html` layout for main page
- **Content**: Primarily `index.md` with included sections

### Core Content Structure
- **Publications**: Managed via `_data/publications.yml` YAML file, rendered through `_includes/publications.md` template
- **Services**: Static content in `_includes/services.md` for reviewer roles
- **Personal Info**: Main content in `index.md` with About Me and Research Interests

### Data Management
Publications are structured in `_data/publications.yml` with these fields:
- `title`, `authors`, `conference`, `conference_short`
- `image` (for paper thumbnails)
- Optional: `pdf`, `code`, `page`, `bibtex`, `notes`

### Styling & Assets
- **SCSS**: `_sass/` contains theme stylesheets (both regular and no-dark-mode variants)
- **Assets**: `assets/` contains images, CSS, JS, and files (like CV PDF)
- **Dark Mode**: Automatic dark mode enabled via `auto_dark_mode: true`

### Theme Customization
- Font choice: Serif/Sans Serif toggle in `_config.yml`
- Colors and layout: Modify `_sass/minimal-light.scss`
- HTML structure: Edit `_layouts/homepage.html`

### Important Files for Content Updates
- `_config.yml`: Personal info, links, SEO settings
- `index.md`: Main page content and news
- `_data/publications.yml`: Publication list data
- `_includes/services.md`: Academic service information

### File Processing
- `html_source_file/` contains compiled HTML (excluded from Jekyll build)
- Publications automatically render with images, links, and citation counts
- Favicon switches based on dark/light mode preference