# Rehbar e Taleem School Website

This repository contains a **single‑page** static website suitable for a school. It uses only HTML, CSS and a tiny amount of vanilla JavaScript (no external libraries) to render a hero banner and a dynamic image gallery. Extra HTML files (`about.html`, `admissions.html`, `gallery.html`, `contact.html`) have been removed; their only purpose was previously to redirect to the main page. The entire stack is free and can be deployed on GitHub Pages (or Netlify) with zero cost.

## Features

- Single‑page sections: Home, About, Achievements, Admissions, Faculty, Life (formerly Gallery), Contact
- Top info bar with address, phone and email visible on every page
- Full‑width hero banner placed outside the main container
- "Life" section shows a grid of photos that are currently hard‑coded in `index.html`; simply edit
  the `<img>` tags directly when you add real photos. You can still drop a `gallery-bg.jpg` in `assets/img/`
  for an optional background image (it will be darkened automatically).
- Template CSS uses simple flex/grid and no external frameworks
- Responsive contact area with a free Formspree form and a fluid Google Map

## Getting Started

1. **Clone the repo** to your local machine.

   ```bash
   git clone <your-repo-url>
   cd "new rehbar e taleem school"
   ```

2. **Replace the logo.**
   - Put a PNG (or SVG) file named `logo.png` in `assets/img/`.
   - The header shows the logo on the left; it links to the home section (`#home`) of the single page.
   - An `<h1>` heading is included for accessibility but hidden visually.

3. **Single‑page structure & placeholder text.**
   - The entire site is now contained in `index.html` with anchor IDs for each section: `#home`, `#about`, `#achievements`, `#admissions`, `#faculty`, `#gallery`, `#contact`.
   - A slim information bar sits above the header and remains visible on scroll.
   - The hero image is moved outside of the `<main>` container so it stretches edge‑to‑edge; content sections also span the full browser width, avoiding any “container” look.
   - The gallery section has been renamed to **Life at Rehbar e Taleem**; update the text and images accordingly. A demonstration script now detects and displays the width×height of each placeholder so you can tell which aspect ratios to shoot.
   - Legacy pages (`about.html`, `admissions.html`, etc.) simply redirect to the appropriate anchor on the main page, so old links will continue to work.
   - Each section already contains example paragraphs that describe what type of real content should go there. The length of the placeholder paragraphs mirrors the expected final content.
   - **Faculty section** lists key staff members only; the old facilities slider and descriptions have been removed. Replace contact cards as needed.
   - (Optional) place a `gallery-bg.jpg` file in `assets/img/` if you want a decorative background behind the Life section; it will darken automatically.
   - Sections are visually separated by alternating backgrounds; the contact area sits in a lighter shaded block above the footer.

4. **Upload pictures** to a free Cloudinary account and copy the public URLs.
   - Create folders such as `school/campus`, `school/events`, etc.
   - After each upload, grab the image URL and add it to `assets/data/images.json`.
   - A mix of dummy images are already present to show a variety of aspect ratios: 4:3, 3:4, 1:1, 16:9, 9:16, 2:1 and 2:3. Those are placed directly in `index.html`; simply edit or replace them with your own URLs (maintain the `width`/`height` attributes to preserve the ratio). The old gallery script has been removed, so the JSON file is no longer required.
   ```json
   [
     "https://via.placeholder.com/1200x800?text=Landscape+4:3",
     "https://via.placeholder.com/800x1200?text=Portrait+3:4",
     "https://via.placeholder.com/1000x1000?text=Square+1:1"
   ]
   ```

   The gallery script will automatically fetch this file and display all URLs listed.

5. **Customize content** in the HTML file as needed (text, contact details).
   - A simple contact form is already included in the #contact section. It uses Formspree to forward submissions to `newrehbaretaleem@gmail.com`. **How to set it up (free):**
     1. Go to https://formspree.io and sign up for a free account (no card needed).
     2. Click "+ New Form" and enter your email address when prompted.
     3. Formspree will generate an endpoint like `https://formspree.io/f/xyz123`.
     4. Copy that URL and paste it into the `action` attribute of the `<form>` element in `index.html`.
     5. Test by submitting the form – you'll receive an email and can confirm the address. The free tier allows up to several hundred submissions per month, which is plenty for a school site.
     6. Optionally configure a custom success message or redirect on the Formspree dashboard.

     This approach keeps everything free and requires no server-side code; all form handling is managed by Formspree.  

4. **View locally** by opening `index.html` in your browser or running a simple HTTP server:

   ```bash
   npx http-server
   ```

5. **Deploy** to GitHub Pages:
   - Push the repository to GitHub.
   - In repo settings, enable GitHub Pages from the `main` branch (or `gh-pages` branch).
   - Optionally configure a custom domain (costs money). Otherwise, use the `https://username.github.io/repo-name` URL.

## Staying 100% Free

- **Hosting**: GitHub Pages / Netlify (free tiers, no credit card).
- **Domain**: use the GitHub subdomain; permanent free custom domains do not exist.
- **Images**: Cloudinary free tier allows enough storage/bandwidth for school photos.
- **Backend**: none. All dynamic behavior is on the client side with JSON.
- **Frameworks**: no React or build tools required.

## Extending the Gallery (Optional)

If you later decide the JSON file maintenance is too manual, you can add a tiny serverless function or use a Cloudinary API call to list all resources in a folder. That would require storing your API key securely (e.g. in Netlify environment variables).

## License

Public domain. Feel free to copy and adapt for your own school.
