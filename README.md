# Portfolio Site

Plain HTML/CSS/JS site — no build step, no Jekyll required. Works on GitHub Pages as-is.

## File structure
```
index.html                     ← homepage (hero, about, skills, project grid, contact)
css/style.css                  ← all styling
js/main.js                     ← nav toggle + scroll animations
projects/
  project-aegis.html
  habitat-rebuild-model.html
  pasadena-ada-assessment.html
  machining-portfolio.html
assets/images/                 ← put your photos/renders here
```

## 1. Before you publish — things to swap out
Search each file for these placeholders and replace them:

- `[Last Name]` / `[LAST NAME]` — your last name, everywhere (nav, titles, footer)
- `your.name@berkeley.edu` — your real email (in `index.html`, Contact section)
- `YOUR-LINKEDIN`, `YOUR-GITHUB` — your actual profile URLs (in `index.html`, Contact section)
- `assets/Ethan_Resume.pdf` — add your resume PDF into `assets/` with that filename, or update the link
- Every `[ Replace with photo/render... ]` block — these are dashed placeholder boxes in each project page. Drop a real image into `assets/images/`, then swap the `<div class="img-placeholder">...</div>` for:
  ```html
  <figure class="img-frame">
    <img src="../assets/images/your-photo.jpg" alt="Describe the image">
    <figcaption>Short caption describing what's shown</figcaption>
  </figure>
  ```

## 2. Publish to GitHub Pages

1. Create a new **public** repo on GitHub — name it `yourusername.github.io` if you want it at the root of your GitHub domain (e.g. `ethanchen.github.io`), or any name if you're fine with a `/reponame/` path.
2. Push these files to the repo (or use the GitHub web UI: **Add file → Upload files**, drag the whole folder in).
3. In the repo, go to **Settings → Pages**.
4. Under **Source**, choose the branch (usually `main`) and folder `/ (root)`. Save.
5. Wait 1–2 minutes — your site will be live at `https://yourusername.github.io` (or `https://yourusername.github.io/reponame/`).

## 3. Custom domain (optional)
If you buy a domain (e.g. from Namecheap):
1. In the domain's DNS settings, add a `CNAME` record pointing to `yourusername.github.io` (for a subdomain like `www.`) — or `A` records pointing at GitHub's IPs for an apex domain (`ethanchen.com`). GitHub's docs list the current IPs.
2. In your repo's **Settings → Pages → Custom domain**, enter your domain and save. GitHub auto-issues HTTPS once DNS propagates (can take up to 24 hrs).

## 4. Adding a new project later
1. Copy `projects/machining-portfolio.html` as a template.
2. Update the title, hero text, specs, body content, and image placeholders.
3. Add a new `<a class="plate">` card in `index.html`'s project grid pointing to your new file.
4. Update the "Next project" links at the bottom of each project page if you want them to chain in a new order.

## 5. Local preview before pushing
Just double-click `index.html` — no server needed, it'll open directly in your browser. (Google Fonts require an internet connection to load properly.)
