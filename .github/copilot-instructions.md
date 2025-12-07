# GitHub Copilot Instructions

## Repository Overview

This repository contains multilingual HTML forms and interactive menus for Verano Estate, a hospitality service. The project focuses on creating accessible, responsive, and visually appealing web interfaces without a build system or framework.

## Project Structure

- `index.html` - Main contact form with language toggle (ES/EN)
- `HTML-MENU.html` - Interactive restaurant menu with TailwindCSS
- `README.md` - Main entry form for guest information
- `.github/workflows/` - GitHub Actions workflow files

## Coding Standards

### HTML
- Use semantic HTML5 elements
- Include proper `lang` attributes (default: `lang="es"`)
- Always include proper meta tags: `charset="UTF-8"` and viewport settings
- Use `data-i18n` attributes for translatable content
- Maintain accessibility with ARIA labels where appropriate

### CSS
- Use CSS custom properties (CSS variables) for theming
- Prefix custom properties with `--` (e.g., `--brand-teal`, `--bg`, `--accent`)
- Use system fonts as fallback: `font-family: system-ui, -apple-system, "Segoe UI", Roboto`
- Include print styles with `@media print` queries
- Maintain responsive design with mobile-first approach

### JavaScript
- Use vanilla JavaScript (no frameworks)
- Store user preferences in `localStorage` (e.g., language selection)
- Use event delegation where appropriate
- Implement i18n with translation objects:
  ```javascript
  const translations = {
    es: { /* Spanish translations */ },
    en: { /* English translations */ }
  };
  ```
- Apply translations using `data-i18n` attributes
- Handle both text content and placeholder attributes for form elements

### Internationalization (i18n)
- Support Spanish (ES) and English (EN) as primary languages
- Use language toggle UI elements (buttons or "cuadrito" boxes)
- Store language preference in localStorage
- Detect browser language as fallback: `navigator.language?.slice(0,2)`
- Apply translations on page load and language change
- Use uppercase language codes in UI (ES, EN)

## Styling Conventions

### Color Schemes
- Verano Estate theme:
  - Primary: `#003C3C` (brand teal)
  - Background: `#FBF7F0` (warm off-white)
  - Text: `#333` or `#222`
  - Accent: `#2b6cb0` (blue)
  
- Menu theme:
  - Background: `#FAFAFB` (fondo)
  - Primary: `#0a0a0a` (negro-azabache)
  - Accent: `#D70040` (rojo-carmin)
  - Secondary: `#40E0D0` (turquesa)

### Font Families
- Sans-serif: Montserrat, Inter, or system-ui
- Serif: Playfair Display (for headings)
- Import fonts from Google Fonts when used

### External Dependencies
- TailwindCSS via CDN: `https://cdn.tailwindcss.com`
- Use latest stable versions
- Prefer CDN over local dependencies for this project

## Development Workflow

### Making Changes
1. This is a static HTML project - no build step required
2. Test changes by opening HTML files directly in a browser
3. Verify multilingual functionality by toggling languages
4. Test responsive design at different viewport sizes
5. Ensure print styles work correctly (for menus)

### Testing
- Manual browser testing (Chrome, Firefox, Safari)
- Test language switching functionality
- Verify localStorage persistence
- Check responsive behavior on mobile devices
- Validate print output for menu files

### Accessibility
- Ensure proper heading hierarchy (h1, h2, h3)
- Include descriptive button text
- Use semantic HTML over divs where possible
- Add ARIA labels for interactive elements
- Maintain sufficient color contrast
- Support keyboard navigation for forms

## File Naming Conventions
- Use lowercase with hyphens for HTML files (e.g., `HTML-MENU.html`)
- Keep file names descriptive and self-documenting
- Use `.html` extension for all HTML files

## Best Practices

### Forms
- Use proper input types (`type="email"`, `type="text"`)
- Include placeholder text in both languages
- Add labels with `for` attributes linking to input ids
- Implement form validation (HTML5 or JavaScript)
- Provide user feedback on submission

### Performance
- Minimize inline styles - use `<style>` blocks
- Load external resources (fonts, CSS) efficiently
- Keep JavaScript execution lightweight
- Avoid unnecessary DOM manipulation

### Maintainability
- Group related styles together
- Comment complex JavaScript logic
- Keep translation objects well-organized
- Use consistent indentation (2 spaces)
- Maintain clean separation of concerns (HTML/CSS/JS)

## Common Patterns

### Language Toggle Implementation
```javascript
// Standard pattern for language switching
const langToggle = document.getElementById('langToggle');
const currentLang = localStorage.getItem('lang') || 'es';

function applyTranslations(lang) {
  document.querySelectorAll('[data-i18n]').forEach(el => {
    const key = el.getAttribute('data-i18n');
    const text = translations[lang][key];
    
    if (el.tagName === 'INPUT' || el.tagName === 'TEXTAREA') {
      el.placeholder = text;
    } else if (el.tagName === 'TITLE') {
      document.title = text;
    } else {
      el.textContent = text;
    }
  });
  
  localStorage.setItem('lang', lang);
}
```

### Form Structure
```html
<form id="contactForm" action="#" onsubmit="event.preventDefault();">
  <label for="fieldId" data-i18n="label_key">Default Text</label>
  <input id="fieldId" name="fieldName" type="text" data-i18n="ph_key" placeholder="Default placeholder">
  <button type="submit" data-i18n="btn_key">Submit</button>
</form>
```

## Notes for AI Assistants

- This is a pure HTML/CSS/JS project with no build system
- Always maintain bilingual support (Spanish and English)
- Preserve existing design themes and color schemes
- Keep code accessible and semantic
- Test changes by viewing HTML files in a browser
- Do not add build tools, package managers, or frameworks unless explicitly requested
- Maintain the lightweight, dependency-free nature of the project
