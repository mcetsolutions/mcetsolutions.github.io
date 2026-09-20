# Mcet Consulting website

Built with [Astro](https://astro.build). Deploys automatically to GitHub
Pages via GitHub Actions on every push to `master`.

## Local development

```
npm install
npm run dev
```

Opens at http://localhost:4321.

## Deploying

1. Push this repo to GitHub (a fresh repo, or reuse the old
   `mcetsolutions.github.io` one — see note below).
2. In the repo, go to **Settings → Pages** and set the source to
   **GitHub Actions** (not "Deploy from a branch").
3. Push to `master` — the included workflow
   (`.github/workflows/deploy.yml`) builds the site and publishes it.
4. Under **Settings → Pages → Custom domain**, enter
   `mcetconsulting.co.uk`. A `CNAME` file is already included in `public/`
   pointing at that domain, so GitHub will pick it up automatically.
5. At your domain registrar, point the domain at GitHub Pages:
   - An `A` record for the apex domain to GitHub's Pages IPs
     (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153), or
   - A `CNAME` record if you're using `www.mcetconsulting.co.uk` instead.
   - GitHub's own docs have the current list, in case it's changed:
     https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

### Reusing the old repo name vs. a new one

If you keep the repo named `mcetsolutions.github.io`, GitHub Pages will
serve it from that address by default, with your custom domain layered on
top via the CNAME file above — so either a fresh repo or the old one works
equally well.

## Contact form

The old site posted to a PHP script (`mail/contact_me.php`), which won't
run on GitHub Pages — Pages only serves static files, no server-side code.
Right now the site just uses a `mailto:` link instead. If you'd like an
actual form later, a service like [Formspree](https://formspree.io) or
[Web3Forms](https://web3forms.com) can handle the submission without you
needing a backend — happy to wire one in when you're ready.

## Structure

```
src/
  components/   one file per section (Header, Hero, Services, About, Contact, Footer)
  layouts/      shared <head> and page shell
  pages/        index.astro assembles the sections
  styles/       global.css — colour, type, and spacing tokens
public/         favicon, CNAME (custom domain)
```
