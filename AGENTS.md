# Agent Guidelines for Portfolio Repository

## Overview
This repository contains a personal portfolio website built with HTML, CSS, and minimal JavaScript. The site is static and does not require a build process.

## Development Commands

### General
- No build process required - open `index.html` directly in a browser
- For local development, use any static server (e.g., `python -m http.server`, `npx serve`, or VS Code Live Server)

### Testing
- Visual testing: Open the site in browsers to check responsiveness and functionality
- No automated test suite exists for this project
- Manual verification checklist:
  - Check all navigation links work
  - Verify theme toggle (light/dark) functions
  - Test mobile menu on narrow viewports
  - Confirm cursor custom effects work
  - Validate all external links open correctly

### Code Quality
- HTML: Validate with W3C validator or similar tool
- CSS: No linting configured; follow style guidelines below
- JavaScript: Basic syntax checking recommended

## Code Style Guidelines

### HTML
- Use semantic HTML5 elements where appropriate
- Indentation: 2 spaces
- Attribute order: `class`, `id`, `name`, `data-*`, `src`, `href`, `alt`, `title`, `aria-*`, then other attributes
- Use lowercase for all tag names and attributes
- Close all tags (including void elements like `<br />`, `<img />`, `<input />`)
- Include lang attribute on `<html>` tag
- Use meaningful, descriptive IDs and classes (kebab-case)
- Add alt text to all images
- Include viewport meta tag for mobile responsiveness

### CSS
- Indentation: 2 spaces
- Selector formatting:
  - Each selector on its own line for multi-selector rules
  - Related properties grouped together
  - Alphabetical order within logical groups (positioning, box model, typography, visual)
- Use CSS custom properties (variables) defined in :root for theme colors
- Prefer logical properties where supported (margin-inline, padding-block, etc.)
- Use `rem` units for typography, `px` for borders and small adjustments, `%` or `fr` for layout
- Comment sections clearly with `/* Section Name */`
- Use BEM-like naming for components: `.block`, `.block__element`, `.block--modifier`
- Mobile-first approach: base styles first, then media queries for larger screens
- Avoid `!important` except for utility classes
- Use CSS custom properties for theming (already implemented)
- Prefer CSS over JavaScript for animations and interactions where possible

### JavaScript/TypeScript
- Indentation: 2 spaces
- Use `const` for variables that don't reassigned, `let` for those that do
- Template literals for string interpolation
- Arrow functions for callbacks
- Destructuring for objects and arrays
- Optional chaining (?.) and nullish coalescing (??)
- Async/await over .then() for promises
- Error handling with try/catch for async operations
- Function naming: camelCase
- Variable naming: camelCase
- Constant naming: UPPER_SNAKE_CASE
- Class naming: PascalCase
- File naming: kebab-case (though only one JS file likely needed)
- Add JSDoc comments for complex functions
- Remove debugger statements before committing
- No console.log in production code (though this is a personal site)

### File Organization
- Keep root directory clean
- Assets (images) should be referenced relatively
- External resources (fonts, icons) loaded efficiently
- Consider separating concerns if JS grows:
  - `js/` directory for scripts
  - `css/` directory for stylesheets (though currently inline)
  - `assets/` for images, icons, etc.

### Performance
- Optimize images (use appropriate format, compress)
- Minify CSS/HTML for production (though not required for this small site)
- Leverage browser caching via headers (server configuration)
- Preload critical resources (fonts)
- Use `loading="lazy"` for offscreen images
- Minimize render-blocking resources
- Consider inlining critical CSS (though currently all in style tag)

### Accessibility
- Ensure sufficient color contrast (already considered in theme variables)
- Keyboard navigable interactive elements
- Proper ARIA labels where needed
- Logical tab order
- Skip to content link (could be added)
- Form labels associated with inputs
- Respect user's prefers-reduced-motion
- Focus visible indicators

### Theme Implementation
- CSS custom properties defined in :root for light theme
- Dark theme overridden via `[data-theme="dark"]` and media query
- Theme toggled by adding/removing `data-theme` attribute on `<html>` element
- Maintain consistency: when adding new colors, define both light and dark variants
- Test both themes thoroughly

### Cursor Effects
- Custom cursor implemented with `#cursor-dot` and `#cursor-ring`
- Ensure these don't interfere with accessibility
- Hide on coarse pointers (touch devices) via media query
- Performance-conscious implementation (using transform/opacity)

## Best Practices

### Incremental Changes
- Make small, focused commits
- Test each change in multiple viewport sizes
- Verify both light and dark themes
- Check performance impact of additions

### Documentation
- Comment complex CSS selectors or JavaScript logic
- Document any non-obvious design decisions
- Keep this AGENTS.md updated as practices evolve

### Maintenance
- Periodically check for broken external links
- Update footer year if needed
- Refresh profile picture and content periodically
- Monitor for browser compatibility issues

## Cursor/Copilot Rules Integration
No specific Cursor or Copilot rules files were found in this repository. Standard GitHub Copilot instructions would apply if used.

When contributing to this repository:
1. Follow the HTML/CSS/JS guidelines above
2. Ensure responsiveness is maintained
3. Test theme functionality
4. Verify no regression in existing features
5. Keep file size and complexity reasonable for a personal portfolio site