# Nuxt 3 Notion

[![Netlify Status](https://api.netlify.com/api/v1/badges/61b93561-607e-4ea9-abdd-035e16185394/deploy-status)](https://app.netlify.com/sites/lustrous-sawine-579ca9/deploys)

Look at the [nuxt 3 documentation](https://v3.nuxtjs.org) to learn more.

## Demo

You can check the demo [here](https://lustrous-sawine-579ca9.netlify.app/)

## Stack

<p align="center">
    <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/nuxtjs/nuxtjs-original.svg" width=32 height=32>
    <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/tailwindcss/tailwindcss-plain.svg" width=32 height=32>
    <img src="https://cdn.worldvectorlogo.com/logos/notion-logo-1.svg" width=32 height=32>
</p>

## Setup

Create an `.env` file
```env
NOTION_ACCESS_TOKEN="your-integration-access-token"
NUXT_PUBLIC_NOTION_ROOT_PAGE="page-you-want-to-render"
```

Make sure to install the dependencies:

```bash
# yarn
yarn install

# npm
npm install

# pnpm
pnpm install --shamefully-hoist
```

## Development Server

Start the development server on http://localhost:3000

```bash
npm run dev
```

## Production

Build the application for production:

```bash
npm run build
```

Locally preview production build:

```bash
npm run preview
```

Checkout the [deployment documentation](https://v3.nuxtjs.org/guide/deploy/presets) for more information.
