# Rehbar e Taleem School Website

This repository contains a **single‑page** static school website built using plain HTML and CSS. There are no build tools or frameworks; everything is authored by hand so the project can be hosted for free on GitHub Pages, Netlify, or a similar static host.

## Key Features

- All content lives in a single `index.html` file with anchored sections: **About**, **Achievements**, **Admissions**, **Faculty**, **Life (gallery)**, and **Contact**.
- A slim information bar sits above a sticky header and remains visible on scroll.
- The full‑width hero banner at the top uses a background image (drop `assets/img/hero.jpg`), with text centered via flexbox.
- The **Life** section displays photos in a flexible wrap layout. Images of different aspect ratios are allowed, and each tag includes `width`/`height` attributes so the browser allocates the correct space before the picture loads.
- The contact form submits to Formspree and clears itself automatically after submission.
- Every email link currently points to `newrehbaretaleem@gmail.com`—replace as needed for actual staff addresses.
- The design uses only CSS (flexbox/grid) and very minimal JavaScript; no external dependencies.

## Editing the Site

1. **Clone the repository:**

   ```bash
   git clone <your-repo-url>
   cd "new rehbar e taleem school"
   ```

2. **Logo:** place `logo.png` (or SVG) in `assets/img/`.

3. **Sections & text:**
   - Modify or replace the placeholder paragraphs in each section directly in `index.html`.
   - The faculty cards are plain `<div>`s with name and email; add/remove entries as necessary.
   - To update the info bar or footer email/phone, change the `<p>` elements near the top or bottom of the file.

4. **Gallery images:**
   - Edit the `<img>` tags inside `#gallery`. Maintain or update the `width`/`height` attributes to reflect the photo's aspect ratio.
   - No additional script or JSON file is required; the layout responds to whatever images you provide.
   - If you would like a background image behind the gallery, drop `gallery-bg.jpg` into `assets/img/`. It will be darkened automatically by the CSS overlay.

5. **Contact form:**
   - Register a free form at [Formspree](https://formspree.io) using your desired email (e.g. `newrehbaretaleem@gmail.com`).
   - Replace the `action` URL in the `<form>` tag with the endpoint Formspree provides.
   - The form resets after submission via a small inline `onsubmit` handler already present.

6. **Local testing:**

   ```bash
   npx http-server
   ```
   or simply open `index.html` in a browser.

7. **Deployment:**
   - Push to GitHub and enable Pages in repository settings (choose `main`/`gh-pages`).
   - Alternatively, drag the repo into Netlify or another static host. Both services have free tiers.

## Email Addresses

All visible email addresses have been updated to use `newrehbaretaleem@gmail.com`. You may change them individually to match real staff accounts. The README itself references that address for the contact form setup.

## Gallery Technical Note

The gallery uses `display: flex` and `flex-wrap: wrap` so items flow naturally. Images come from `picsum.photos` placeholders by default; update the `src` attributes with your own URLs as you add actual school photos.

## Keeping It Free

- Hosting: GitHub Pages or Netlify.
- Images: Cloudinary free tier works well if you need cloud storage, but local files are fine too.
- No server code – form handling is outsourced to Formspree so there’s no backend to maintain.

## License

Public domain. Use or modify this project freely for your own school or educational organization.
