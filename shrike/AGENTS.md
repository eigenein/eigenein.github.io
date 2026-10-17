# Shrike

A static web page served from `shrike/index.html`.

## Dependencies

All third-party resources are loaded from [cdnjs](https://cdnjs.cloudflare.com) with Subresource Integrity (`integrity`, `crossorigin="anonymous"`, `referrerpolicy="no-referrer"`):

| Library                                   | Version | File                  |
|-------------------------------------------|---------|-----------------------|
| [Bulma](https://bulma.io)                 | 1.0.4   | `css/bulma.min.css`   |
| [Font Awesome](https://fontawesome.com)   | 7.3.1   | `css/all.min.css`     |

When upgrading, take the latest version from cdnjs (`https://api.cdnjs.com/libraries/<name>?fields=version`) and update the SRI hash (`https://api.cdnjs.com/libraries/<name>/<version>?fields=sri`) together with the URL.

## Theming

Bulma follows the device light/dark preference automatically through `prefers-color-scheme`. Keep it that way:

- `<meta name="color-scheme" content="light dark">` is set in the head so native UI (scrollbars, form controls) matches.
- Do **not** add `data-theme` or `.theme-light`/`.theme-dark` to `<html>` or `<body>`: these would pin the theme and override the device preference.

## Styling

- Use Bulma classes, helpers, and CSS variables for layout and appearance, and Font Awesome for icons.
- Do **not** add custom CSS (`<style>`, `style=""`, or extra stylesheets) unless explicitly requested, or a proposal to do so has been approved.

## Accessibility

- Keep `lang` on `<html>` and a meaningful `<title>`.
- Use semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<footer>`, `<section>`, etc.) and a sensible heading hierarchy.
- Use ARIA attributes where semantics alone are insufficient, for example `aria-label` on icon-only buttons and links, `aria-expanded`/`aria-controls` on toggles (such as the Bulma navbar burger), and `role` only when no native element fits.
- Mark decorative Font Awesome icons with `aria-hidden="true"`. Give meaningful icons an accessible name through adjacent text or an `aria-label` on the parent control.
- Every form control needs an associated `<label>` (or `aria-label`), and images need `alt` text (`alt=""` if decorative).
