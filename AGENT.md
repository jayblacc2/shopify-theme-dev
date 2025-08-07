# Agent Development Guide

## Build/Test Commands
- No specific build commands - uses Shopify CLI: `shopify theme dev` (development), `shopify theme push` (deploy)
- TailwindCSS via CLI: `npx tailwindcss -o assets/output.css` (if needed)
- No test suite configured - add with `npm test` if implementing

## Architecture
- **Type**: Shopify Liquid theme based on Dawn/Online Store 2.0
- **Structure**: Standard Shopify theme directories - sections/ (reusable components), templates/ (page types), snippets/ (reusable code), assets/ (CSS/JS/images), config/ (theme settings), locales/ (translations)
- **Styling**: TailwindCSS utility classes throughout Liquid templates
- **JavaScript**: Native browser features preferred, minimal dependencies

## Code Style & Conventions
- **Liquid**: Follow {% liquid %} blocks for multiline, use proper filter/tag syntax from copilot-instructions.md
- **CSS**: BEM naming (block__element--modifier), mobile-first media queries, CSS variables in :root
- **HTML**: Semantic elements, CamelCase IDs with section/block suffixes, accessibility-first
- **Naming**: snake_case for Liquid variables, kebab-case for CSS classes
- **Comments**: Minimal, use {% # %} for Liquid inline comments

## Shopify Development Rules
- All filters/tags/objects must be valid Shopify Liquid (see .github/copilot-instructions.md)
- Section schemas required for theme editor customization
- Server-side rendering preferred over client-side JavaScript
- Use translation keys {{ 'key' | t }} for all user-facing text
