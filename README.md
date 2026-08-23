# Maikeru's Blog

This is the source for [maikeru.github.io](https://maikeru.github.io/), a Gatsby site containing notes about software development, technology, and other things I've done.

## Development

Requirements:

- Node.js 18 or newer
- pnpm 10 (the repository pins the expected version through `packageManager`)

Install dependencies and start the local development server:

```shell
pnpm install
pnpm run develop
```

The site is available at [http://localhost:8000](http://localhost:8000). Gatsby's GraphiQL explorer is available at [http://localhost:8000/\_\_\_graphql](http://localhost:8000/___graphql).

To create a production build locally:

```shell
pnpm run clean
PREFIX_PATHS=true pnpm run build
```

The generated site is written to `public/`. To serve that build locally, run:

```shell
pnpm run serve
```

## Content

Blog posts live in [`content/blog`](content/blog) as Markdown files. Gatsby creates the post pages, RSS feed, and responsive image assets during the build.

## Deployment

GitHub Actions builds and deploys the site to GitHub Pages when changes are pushed to `master`. The workflow is defined in [`.github/workflows/gatsby.yml`](.github/workflows/gatsby.yml) and uses the same pnpm install and production build commands shown above.
