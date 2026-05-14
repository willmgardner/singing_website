# williamgardnertenor.com

Static rebuild of the William Gardner | Tenor website, archived from
Squarespace. Plain HTML/CSS — no build step, no JS framework.

## Structure

```
.
├── index.html        Homepage (greeting + headshot)
├── bio.html
├── events.html       Performance archive 2017–2019
├── photos.html       Production / performance gallery
├── audio.html        7 recordings (MP3 / M4A)
├── video.html        YouTube embeds
├── contact.html
├── CNAME             williamgardnertenor.com (for GitHub Pages)
├── .nojekyll         Tells GH Pages to skip Jekyll processing
└── assets/
    ├── css/site.css
    ├── img/          12 JPEGs (~20 MB)
    └── audio/        7 MP3/M4A files (~32 MB)
```

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploying to GitHub Pages

1. Create a new repo on GitHub (any name; for clarity, `williamgardnertenor`).
2. From this directory:

   ```sh
   git init
   git add .
   git commit -m "Initial static rebuild"
   git branch -M main
   git remote add origin git@github.com:<your-username>/williamgardnertenor.git
   git push -u origin main
   ```

3. In the repo, go to **Settings → Pages** and set the source to
   `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Add a custom domain: `williamgardnertenor.com`. The `CNAME` file is
   already in the repo.
5. In your domain registrar's DNS settings, point the domain at GitHub Pages:
   - Apex `williamgardnertenor.com` → `A` records to
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www.williamgardnertenor.com` → `CNAME` to `<your-username>.github.io`
6. Enable **Enforce HTTPS** in Pages settings once the cert provisions
   (usually within an hour).
7. Cancel Squarespace once DNS has propagated and the GH Pages site is
   serving the domain correctly.

## Notes on the archive

- All media is committed to the repo, so the site is fully self-contained
  and will continue to work after the Squarespace subscription is canceled.
