# Shrike

The product page for the Shrike Mac app, served by GitHub Pages at <https://eigenein.dev/shrike>. It is plain static files with no build step: `shrike/index.html` and `shrike/style.css`.

## Fixed URLs

The app and App Store Connect link to this page, so keep these working:

- `https://eigenein.dev/shrike` is the app's **Shrike Help** link and the App Store Connect Support URL.
- `https://eigenein.dev/shrike#privacy` is the app's **Privacy Policy** link and the App Store Connect Privacy Policy URL, so the policy section must keep `id="privacy"`.
- `shrike@eigenein.dev` is the support address.

The privacy policy covers the Shrike app only, not this website. Keep it in line with what the app actually does, and update its "Last updated" date when the content changes.

## Before launch

- Replace the favicon (the inline SVG `<link rel="icon">` in the head) and the wordmark icon in the top bar (`.mark`) with the app icon. Both are placeholders for now.
- Replace the "Coming soon to the Mac App Store" slot (`.store`) with Apple's official "Download on the Mac App Store" badge, unmodified, linking to the app's App Store page.

## Images

- The hero (`.stage`) is an HTML/CSS illustration of a redacted image, not the app's UI. Don't dress it up as an app window.
- `screenshot-light.webp` and `screenshot-dark.webp` are real captures of the app window in each appearance, and the page picks one through `<picture>` and `prefers-color-scheme`. Take both of the same state at 2× resolution, with the macOS window shadow on a transparent background (⌘⇧4, then Space), and convert them with `cwebp -lossless -z 9 -metadata none`. Retake them when the app's UI changes, and keep the `alt` text and the copy around them in line with what they show.

## Dependencies

There are none: no CSS frameworks, icon fonts, web fonts, or scripts. Fonts come from the system font stack, and icons are inline SVG. Keep it that way unless a dependency is clearly worth it, because every third-party host also sees visitors' IP addresses.

## Styling

- All styles live in `style.css`. Avoid `<style>` blocks and `style=""` attributes.
- Colours, fonts, and spacing are CSS custom properties on `:root`. Use them instead of hard-coded values.
- Light and dark themes follow the device through `prefers-color-scheme`, which overrides the custom properties. Do not add a theme switch or pin a theme. `<meta name="color-scheme" content="light dark">` stays in the head.
- Animations must stop under `prefers-reduced-motion: reduce`.
- Layouts must work from phone width up, with no horizontal scrolling.

## Accessibility

- Keep `lang` on `<html>` and a meaningful `<title>`.
- Use semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<footer>`, `<section>`, etc.) and a sensible heading hierarchy.
- Mark decorative SVGs and illustrations with `aria-hidden="true"`. Give images meaningful `alt` text (`alt=""` if decorative).
- Keep interactive elements keyboard accessible with a visible focus style.
