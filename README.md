# YuShan Hung Portfolio

The next version of this portfolio is being built with Astro and TypeScript. The existing static site remains intact in the repository while the Astro deployment migration is reviewed and verified.

## Local setup

Use Node.js 22.12 or newer (with npm 9.6.5 or newer), then install dependencies:

```sh
npm install
```

## Development commands

```sh
npm run dev      # Start the local development server
npm run check    # Run Astro and TypeScript diagnostics
npm run build    # Create a production build in dist/
npm run preview  # Preview the production build locally
```

Astro is configured for the GitHub Pages user site at `https://haneyoshi.github.io/`. Pushes to `main` run the project checks and production build, then deploy only the generated `dist/` directory through the official GitHub Pages actions.
