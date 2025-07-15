# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a minimalist personal website (lorie.do) built with Eleventy (11ty) static site generator. The site features a simple, responsive design with dark/light theme toggle and dynamic adjective rotation.

## Development Commands

```bash
# Start development server with live reload
npm start
# or
npx @11ty/eleventy --serve

# Build for production
npm run build
# or
npx @11ty/eleventy
```

The development server runs at `http://localhost:8080` with automatic rebuilding on file changes.

## Project Structure

```
src/
├── _includes/
│   └── base.njk          # Main layout template with theme toggle and dynamic adjective scripts
├── index.md              # Homepage content (Markdown with frontmatter)
├── style.css             # CSS with CSS custom properties for theming
├── adjectives.json       # JSON data file with adjectives for dynamic rotation
└── favicon files         # Various favicon formats
```

## Architecture

- **Static Site Generator**: Eleventy with ES module configuration
- **Templating**: Nunjucks (.njk) for layouts, Markdown for content
- **Styling**: Vanilla CSS with CSS custom properties for theming
- **JavaScript**: Vanilla JS embedded in template for theme toggle and dynamic content
- **Build Output**: Generated to `_site/` directory

## Key Features

1. **Theme System**: Uses CSS custom properties with localStorage persistence. Dark theme is default.
2. **Dynamic Adjectives**: JavaScript fetches adjectives.json and randomly updates `.dynamic-adjective` spans on page load.
3. **Responsive Design**: Uses viewport-based font sizing (vh/vw units) and CSS Grid for centering.

## File Passthrough

The Eleventy config copies these files directly to output:
- CSS styles
- Favicon files (multiple formats)
- adjectives.json data file

## Content Management

- Page content is in `src/index.md` with YAML frontmatter
- Layout template is `src/_includes/base.njk`
- Adjectives for dynamic rotation are in `src/adjectives.json`