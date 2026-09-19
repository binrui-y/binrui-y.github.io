# Personal academic website

A single static page — no build tools, no dependencies to install. Ready to
push straight to GitHub Pages.

## Structure

```
index.html              The whole site: name banner, photo/intro, Research, Teaching, Education
assets/css/style.css     All styling — colors, fonts, spacing
assets/images/           Put your headshot here
assets/files/             Put your CV and paper PDFs here
```

## 1. Fill in your real content

Open `index.html` in any text editor and replace the placeholders:

- Your name (appears twice: the big banner at the top, and the `<title>` tag)
- Affiliation line, intro paragraph
- Email address (two places — the `mailto:` link and the "Request draft" link)
- Social/profile links (Google Scholar, GitHub, LinkedIn — add or remove any)
- Each paper's title, coauthors, abstract, and file links
- Teaching rows and Education rows

Then add your headshot to `assets/images/`, and replace this block in
`index.html`:

```html
<div class="headshot" aria-hidden="true">photo</div>
```

with:

```html
<img class="headshot" src="assets/images/your-photo.jpg" alt="Jane Doe">
```

(You'll also want to remove the `.headshot` background-gradient rule in
`style.css` once you're using a real photo — it's just a placeholder look.)

Finally, put your CV and paper PDFs in `assets/files/`, matching the
filenames already linked in `index.html` (or edit the links to match your
filenames).

## 2. Create the GitHub repository

1. Go to [github.com/new](https://github.com/new) and create a new repository.
   - If you want the site at `https://yourusername.github.io` (the shortest
     possible URL), name the repository exactly `yourusername.github.io`.
   - If you're fine with a URL like `https://yourusername.github.io/site`,
     name it anything you like (e.g. `academic-site`).
2. Leave it public, and don't initialize it with a README (you already have
   one).

## 3. Push your files

From the folder containing `index.html`, run:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/yourusername/yourrepo.git
git push -u origin main
```

Replace `yourusername/yourrepo` with your actual GitHub username and
repository name.

(If you'd rather not use the command line, you can also drag-and-drop all
the files into the empty repository through the GitHub web interface, using
"Add file → Upload files.")

## 4. Turn on GitHub Pages

1. In your repository on GitHub, go to **Settings → Pages** (left sidebar).
2. Under "Build and deployment" → **Source**, choose **Deploy from a
   branch**.
3. Under **Branch**, select `main` and `/ (root)`, then click **Save**.
4. Wait a minute or two. Refresh the Pages settings page — a banner will
   show your live URL:
   - `https://yourusername.github.io` (if you named the repo that way), or
   - `https://yourusername.github.io/yourrepo`

That URL is now your live site.

## 5. Making changes later

Any time you edit `index.html`, `style.css`, or add new files:

```bash
git add .
git commit -m "Update site"
git push
```

GitHub Pages rebuilds automatically within a minute or so of each push.

## Notes

- The fonts (Fraunces and Source Serif 4) load from Google Fonts over the
  network, so they'll display correctly once the site is live — this only
  fails in offline previews.
- Everything — colors, spacing, type sizes — is controlled from the
  `:root { ... }` variables at the top of `assets/css/style.css`, so you can
  retune the palette without touching the rest of the file.
