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

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages** and set the source to
   **GitHub Actions** (not "Deploy from a branch").
3. Push to `master` — the included workflow
   (`.github/workflows/deploy.yml`) builds the site and publishes it.
4. Under **Settings → Pages → Custom domain**, enter your domain name. Update the `CNAME` file in `public/`
   to point at that domain, so GitHub will pick it up automatically.
5. At your domain registrar, point the domain at GitHub Pages:
   - An `A` record for the apex domain to GitHub's Pages IPs
     (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153), or
   - A `CNAME` record if you're using a custom domain instead.
   - GitHub's own docs have the current list, in case it's changed:
     https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

## Structure

```
src/
  components/   one file per section (Header, Hero, Services, About, Contact, Footer)
  layouts/      shared <head> and page shell
  pages/        index.astro assembles the sections
  styles/       global.css — colour, type, and spacing tokens
public/         favicon, CNAME (custom domain)
```
