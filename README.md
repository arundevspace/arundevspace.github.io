# Arun Kumar Arasappan — Portfolio

Personal portfolio site. Plain HTML, CSS and a little JavaScript, no build step.
Hosted free on GitHub Pages and deployed automatically by GitHub Actions on every push to `main`.

```
site/
  index.html                         the portfolio
  Arun_Kumar_Arasappan_Resume.pdf    linked from the Download Résumé buttons
  404.html                           shown for unknown URLs
  robots.txt
.github/workflows/deploy.yml         builds and publishes site/ to GitHub Pages
```

## Deploy (one time, ~10 minutes, free)

1. **Create the repo.** On GitHub, create a new **public** repository.
   - Name it `<your-username>.github.io` to get the clean URL `https://<your-username>.github.io`.
   - Any other name works too; the site then lives at `https://<your-username>.github.io/<repo-name>/`.
   - Leave "Add a README" unticked.

2. **Push these files.** From this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```

3. **Turn on Pages.** In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.

4. **Run the deploy.** Open the **Actions** tab. If the first run failed because Pages was off, click it and choose **Re-run all jobs**. When it goes green, the run shows your live URL.

From now on, every push that changes `site/` redeploys in about a minute.

## Updating

- Edit `site/index.html`, commit, push. That's it.
- New résumé: replace `site/Arun_Kumar_Arasappan_Resume.pdf` with the same file name.
- Preview locally: `python3 -m http.server -d site 8000` and open http://localhost:8000.

## Optional: custom domain

GitHub Pages hosting stays free with your own domain; only the domain itself costs money (roughly ₹800–1,500/year for a `.dev` or `.in`).

1. Buy the domain from any registrar (Cloudflare Registrar sells at cost).
2. Add a file `site/CNAME` containing just the domain, for example `arunkumar.dev`.
3. At the registrar, add DNS records:
   - Apex domain: four `A` records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www`: a `CNAME` record to `<your-username>.github.io`
4. In **Settings → Pages**, enter the domain and tick **Enforce HTTPS** once the certificate is issued (can take up to an hour).

## Privacy note

The résumé PDF includes your phone number and is publicly downloadable once deployed. If you'd rather not publish it, export a copy without the number and replace the PDF before pushing.
