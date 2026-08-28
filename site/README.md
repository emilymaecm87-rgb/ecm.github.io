# Personal website

Plain HTML + one stylesheet. No build step, no dependencies, nothing to install.

```
index.html      About
research.html   Publications, work in progress, projects, policy writing
teaching.html   Teaching experience
cv.html         Full CV
style.css       All styling (colors live in the :root block at the top)
assets/
  photo.jpg        <- replace with a real headshot (square, ~600x600)
  emily-ma-cv.pdf  <- swap in an updated CV any time, same filename
```

## Editing

Open any `.html` file in a text editor. Each entry looks like this:

```html
<div class="entry">
  <div class="when">2024</div>
  <div class="what">
    <h3>Title</h3>
    <p class="role">Authors — <em>Journal</em>, volume.</p>
    <p>Description.</p>
  </div>
</div>
```

Copy the block, change the text. To change colors or fonts, edit the
`:root` variables at the top of `style.css` — the dark-mode block right
below it mirrors them.

To preview locally: `python3 -m http.server 8000` in this folder, then
open http://localhost:8000

## Deploying to GitHub Pages

1. Create a **public** repo named exactly `<your-username>.github.io`
   (e.g. `emilyma.github.io`). Don't add a README during creation.
2. In this folder:

   ```bash
   git init -b main
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
   git push -u origin main
   ```

3. Repo → **Settings → Pages** → Source: *Deploy from a branch*,
   Branch: `main`, folder: `/ (root)`. Save.
4. Live at `https://<your-username>.github.io` in a minute or two.

Every later `git push` republishes automatically.

### Custom domain (optional)

Add a file named `CNAME` containing just the domain (e.g. `emilyma.com`),
then point a CNAME DNS record at `<your-username>.github.io`. Enter the
domain under Settings → Pages and tick "Enforce HTTPS".
