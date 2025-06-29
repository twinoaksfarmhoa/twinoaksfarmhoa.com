# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the Twin Oaks Farm HOA website - a static site for a 213-home residential community in Woodbridge, Virginia. Built with Eleventy (11ty) v3.1.2 and TailwindCSS v3.0.24, it serves as an information hub for residents.

## Development Commands

```bash
# Install dependencies
npm install

# Development server with hot reload
npm run serve

# Production build
npm run build

# Clean build directory
npm run clean
```

## Architecture & Key Concepts

### Tech Stack
- **Eleventy (11ty)**: Static site generator using Nunjucks templating
- **TailwindCSS**: Utility-first CSS framework with dark mode support
- **Webpack**: Bundles JavaScript and processes CSS through PostCSS
- **Node.js**: Runtime environment

### Directory Structure
- `src/_data/`: Global data files (contact.json, minutes.json)
- `src/_includes/`: Templates and components
- `src/pages/`: Content pages with front matter
- `src/docs/`: PDF documents (meeting minutes, HOA documents)
- `_site/`: Generated output (gitignored)

### Key Configuration Files
- `.eleventy.js`: Configures navigation plugin, passthrough copies, and date filters
- `webpack.config.js`: Entry points for JS/CSS bundling
- `tailwind.config.js`: Dark mode via class, content path scanning

### Development Patterns

1. **Templates**: Use Nunjucks (.njk) with Eleventy front matter for metadata
2. **Navigation**: Automatic menu generation via Eleventy Navigation plugin
3. **Data Access**: Files in `_data/` are globally accessible in templates
4. **Dark Mode**: Toggle implementation with localStorage persistence
5. **Responsive Design**: Mobile-first using Tailwind responsive utilities

### Important Data Structures

**contact.json**: Contains board members, committees, management company, and service numbers
**minutes.json**: Meeting minutes archive organized by year (2009-2022)

### Common Tasks

When updating contact information:
- Edit `src/_data/contact.json`
- Board members, committees, and service numbers are rendered automatically

When adding meeting minutes:
- Place PDF in `src/docs/minutes/YYYY/`
- Update `src/_data/minutes.json` with new entry

When creating new pages:
- Add to `src/pages/` with appropriate front matter
- Include `eleventyNavigation` for menu inclusion