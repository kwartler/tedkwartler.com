# tedkwartler.com

Personal and professional site for **Ted Kwartler** (Managing Director of Responsible AI at Accenture, Harvard Extension School instructor, author).

Static site, no build step. Just HTML, one CSS file, and images. Hosted on **GitHub Pages** with a custom domain.

## Structure

```
index.html          Main page (all sections)
404.html            Custom not-found page
assets/style.css    Design system + all styling
assets/favicon.svg  Site icon (TK monogram)
assets/og-image.png Social-share preview image (1200x630)
CNAME               Custom domain for GitHub Pages
robots.txt          Search-engine crawl rules
sitemap.xml         Sitemap for search engines
.nojekyll           Tells GitHub Pages to serve files as-is
```

## SEO built in

- Descriptive `<title>`, meta description, and keywords
- Open Graph + Twitter Card tags with a branded preview image
- JSON-LD `Person` structured data with `sameAs` links (LinkedIn, X, GitHub, Harvard, DataCamp, WEF, Amazon, rstatsbook), which helps Google build a knowledge panel
- Canonical URL, `robots.txt`, and `sitemap.xml`
- Cross-links to [rstatsbook.com](https://www.rstatsbook.com/) and [LLMBA](https://llmba.com/)

## Deploy to GitHub Pages

1. This repo is already pushed to `github.com/kwartler/tedkwartler.com`.
2. In the repo: **Settings -> Pages**. Under **Build and deployment**, set **Source: Deploy from a branch**, **Branch: `main` / `root`**, then **Save**.
3. The `CNAME` file already sets the custom domain to `tedkwartler.com`. GitHub will verify it.
4. Point your DNS at GitHub Pages (see below). Enable **Enforce HTTPS** once the certificate is issued (can take a few minutes to an hour).

## DNS setup (at your domain registrar)

For the apex domain `tedkwartler.com`, create four **A records** pointing to GitHub Pages:

```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```

And a **CNAME record** so the www version works too:

```
CNAME   www   kwartler.github.io
```

(Optional, recommended) Add the IPv6 AAAA records as well:

```
AAAA  @  2606:50c0:8000::153
AAAA  @  2606:50c0:8001::153
AAAA  @  2606:50c0:8002::153
AAAA  @  2606:50c0:8003::153
```

Once DNS propagates, remove your old paid hosting.

## Editing

Everything is plain HTML/CSS, so edit `index.html` and `assets/style.css` directly and push. Change the colors by editing the CSS variables at the top of `style.css`.

To update the social-share image, replace `assets/og-image.png` (keep it 1200x630).
