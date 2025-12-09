# Copilot Instructions for index-html-html Repository

## Project Overview

This repository contains HTML-based web forms and interactive interfaces for **Verano Estate**, a vacation rental property managed by Chef Franko. The project includes:

- Guest information collection forms
- Interactive menu displays
- Multilingual support (Spanish and English)
- WhatsApp integration for form submissions
- Wedding/event planning dashboards

## Repository Structure

- `index.html` - Main guest information form with language toggle
- `README.md` - Detailed form HTML (appears to be a complete guest form)
- `HTML-MENU.html` - Interactive menu display system
- `untitled-1.html` - Wedding event planning dashboard
- `.github/workflows/` - GitHub Actions workflows

## Technology Stack

- **Pure HTML5, CSS3, and Vanilla JavaScript** - No build tools or package managers
- **Tailwind CSS** - Via CDN for styling
- **Chart.js** - Via CDN for data visualization
- **Google Fonts** - Playfair Display (serif) and Inter/Montserrat (sans-serif)

## Code Conventions

### HTML Structure
- Use semantic HTML5 elements
- Follow proper document structure with `<!DOCTYPE html>`
- Include proper `<meta>` tags for charset and viewport
- Use `data-i18n` attributes for translatable text elements

### CSS Styling
- Use Tailwind CSS utility classes as the primary styling method
- Define custom CSS variables in `:root` for brand colors:
  - Primary brand color (teal): `#003C3C` or `--brand-teal`
  - Background: `#FBF7F0` or `--brand-bg`
- Use inline `<style>` tags for custom CSS
- Maintain responsive design with mobile-first approach

### JavaScript Patterns
- Use vanilla JavaScript (ES6+)
- Wrap code in `DOMContentLoaded` event listeners
- Follow camelCase naming convention for functions and variables
- Use `const` and `let` instead of `var`
- Implement i18n using object dictionaries (e.g., `translations` object)

### Language Support
- Default language: Spanish (`es`)
- Secondary language: English (`en`)
- Use `data-i18n` attributes on elements that need translation
- Implement language toggle buttons with visual active state
- Translation keys should be descriptive (e.g., `formTitle`, `basicInfo`)

### Form Handling
- Use semantic form inputs with proper `name` attributes
- Implement WhatsApp integration for form submissions
- Format WhatsApp messages with sections using markdown-style formatting
- Include proper validation and user feedback
- Use FormData API for collecting form data

## Brand Guidelines

### Typography
- **Headings**: Playfair Display (serif, bold)
- **Body text**: Inter or Montserrat (sans-serif)
- Font weights: 400 (regular), 500 (medium), 600 (semi-bold), 700 (bold)

### Color Palette
- **Primary**: Teal `#003C3C` (brand color)
- **Background**: Warm beige `#FBF7F0`
- **Accent**: Lighter teal `#4c7c7c`
- **Text**: Dark gray `#333` or `#222`
- **Borders**: Light gray `#D1D5DB` or `#e5e7eb`

### Button Styles
- Primary buttons: Dark teal background with white text
- Secondary buttons: Lighter teal background
- Include hover states with subtle color darkening
- Add transition effects for smooth interactions

## Common Tasks

### Adding a New Form Field
1. Add the input field with proper `name` attribute
2. Add a `<label>` with descriptive text
3. If translatable, add `data-i18n` attribute to the label
4. Update the translation object with new keys for both languages
5. Include the field in the WhatsApp message formatting function

### Adding a New Language
1. Update the `translations` object with a new language key
2. Add all translation strings for the new language
3. Create a new language toggle button
4. Update the `setLanguage()` function to handle the new language

### Modifying WhatsApp Integration
- Phone number format: Include country code (e.g., `523221606843`)
- Use `encodeURIComponent()` for message content
- Format messages with emojis and markdown-style headers
- Open in new tab with `target="_blank"`

### Styling Components
- Use Tailwind utility classes first
- For custom styles, define them in the `<style>` tag within `<head>`
- Maintain consistency with existing component styles
- Follow the established color scheme and spacing

## File Naming
- Use lowercase with hyphens for HTML files (kebab-case)
- Keep file names descriptive but concise
- Avoid special characters except hyphens

## Testing
- Test all forms in both Spanish and English
- Verify WhatsApp link formatting on mobile devices
- Check responsive design on mobile, tablet, and desktop viewports
- Validate HTML using W3C validator when possible

## Important Notes

- **No build process**: All changes are directly to HTML files
- **CDN dependencies**: External libraries loaded via CDN, not npm
- **Direct deployment**: Files are served as static HTML
- **Mobile-first**: Forms are designed primarily for mobile users
- **WhatsApp is critical**: Ensure all form integrations maintain working WhatsApp functionality

## Contact Information

- Business: Verano Estate by Chef Franko
- WhatsApp: +52 322 160 6843
- Email: franko@veranostate.com
- Instagram: @veranostate

## Best Practices

1. **Keep it simple**: This is a static HTML project, avoid overcomplicating with unnecessary frameworks
2. **Maintain consistency**: Follow existing patterns for forms, buttons, and layouts
3. **Bilingual first**: Always consider both Spanish and English when adding features
4. **Test WhatsApp links**: These are the primary CTA, ensure they work correctly
5. **Responsive design**: Test on multiple screen sizes
6. **Accessibility**: Use semantic HTML and proper ARIA labels where needed
7. **Performance**: Keep CDN usage minimal, inline critical CSS when appropriate
