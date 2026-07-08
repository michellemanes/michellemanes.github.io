# Michelle Manes — personal website (Quarto)

A clean, accessible personal academic site built with [Quarto](https://quarto.org).
It's designed to be portable: it lives on a domain *you* own, so it follows you
across jobs.

---

## What's here

```
_quarto.yml      Site config: title, navbar, theme, page settings
custom.scss      Accessibility overrides (contrast, focus states, type size)
index.qmd        Home / bio
research.qmd     Research + publications
teaching.qmd     Teaching
outreach.qmd     Education & outreach
images/          Put headshot.jpg (and any other images) here
cv/              Put manes-cv.pdf here
```

You edit the `.qmd` files (plain text with Markdown). Everything between the
`---` fences at the top is settings; everything below is your content.

---

## One-time setup

1. **Install Quarto** — download from <https://quarto.org/docs/get-started/>
   (there's a normal Mac installer; no command line needed to install).
2. **Add your files**
   - Put a photo at `images/headshot.jpg`
   - Put your CV at `cv/manes-cv.pdf`
3. **Open a terminal in this folder** and preview the site:
   ```
   quarto preview
   ```
   This opens the site in your browser and live-reloads as you edit. Fill in
   the placeholders marked with `<!-- comments -->` in each `.qmd` file.

To produce the final files for hosting:
```
quarto render
```
This writes the finished website into a `_site/` folder.

---

## Getting a permanent home (the important part)

The permanence comes from **owning a domain**, not from any one host.

### 1. Register a domain (~$10–15/year)
Use a registrar such as **Cloudflare**, **Namecheap**, or **Porkbun**.
Pick something like `michellemanes.com` (or `.org` / `.net`). This name is
yours and never changes, no matter where you work or who hosts the site.

### 2. Host the site for free
Recommended: **Netlify** or **Cloudflare Pages**. Both are free for a site
like this and both let you attach your custom domain.

Fastest path (no GitHub required):
- Run `quarto render` to produce the `_site/` folder.
- Go to Netlify → "Add new site" → "Deploy manually" → **drag the `_site`
  folder** onto the page. It's live in seconds on a temporary Netlify URL.
- In Netlify's **Domain settings**, add your custom domain and follow the
  DNS instructions (Netlify walks you through it).

When you update the site later, `quarto render` again and re-drag `_site`.

> Note: Quarto's own **Quarto Pub** is even simpler (`quarto publish quarto-pub`)
> but it does **not** support custom domains — so it's fine for a quick preview,
> not for the permanent home you want.

### 3. Redirect your old page (optional but nice)
Once the new site is live, ask UH to put a redirect (or a single line linking
to your new domain) at `math.hawaii.edu/~mmanes` so old links still find you.

---

## Editing tips

- **Publications:** start by typing them by hand in `research.qmd`. If the list
  gets long, switch to a `references.bib` file (Quarto renders BibTeX natively).
- **New page:** create `something.qmd`, then add it to the `navbar` in
  `_quarto.yml`.
- **Math:** LaTeX works inline with `$...$` and display with `$$...$$`.
- **Accessibility:** always give images alt text (`fig-alt="..."`), keep the
  light theme, and don't rely on color alone to convey meaning.
