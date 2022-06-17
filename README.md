# Nuxt 3 Notion

[![Netlify Status](https://api.netlify.com/api/v1/badges/61b93561-607e-4ea9-abdd-035e16185394/deploy-status)](https://app.netlify.com/sites/lustrous-sawine-579ca9/deploys)

## Table of contents

-   [Front-end Example (Nuxt)](#front-end-example)
-   [Back-end Example (Notion)](#back-end-example)
-   [Documentation](#documentation)
-   [Stack](#stack)
-   [Setup](#setup)
-   [Development Server](#development-server)
-   [Production](#production)

## Front-end example

This app is rendering a notion page, which you can see [here](https://lustrous-sawine-579ca9.netlify.app/).

## Back-end example

How this page looks on Notion you can find [here](https://wide-hat-401.notion.site/Nuxt-3-Notion-b48f95480a714640a2dd0668aed3b7da).

## Stack

<p align="center">
    <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/nuxtjs/nuxtjs-original.svg" width=32 height=32>
    <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/tailwindcss/tailwindcss-plain.svg" width=32 height=32>
    <img src="https://cdn.worldvectorlogo.com/logos/notion-logo-1.svg" width=32 height=32>
</p>

## Documentation

Look at the [Nuxt 3 documentation](https://v3.nuxtjs.org), [Tailwind documentation](https://tailwindcss.com/docs/installation) and [Notion API documentation](https://developers.notion.com/reference/intro) to learn more.
This application is also using [DaisyUI](daisyui.com), a TailwindCSS component library.

## Setup

1. Clone this repository

```sh
git clone https://github.com/egrzeszczak/nuxt-3-notion
```

2. Create an `.env` file in the root folder

```env
NOTION_ACCESS_TOKEN="your-integration-access-token"
NUXT_PUBLIC_NOTION_ROOT_PAGE="page-you-want-to-render"
```

3. Delete `layouts/` folder

4. Replace the existing `/pages/index.vue` file with:

```html
<script setup>
	const config = useRuntimeConfig();
	navigateTo(`/page/${config.notionRootPage}`);
</script>
```

5. Make sure to install the dependencies:

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
npx nuxi dev
```

## Production

Build the application for production:

```bash
npx nuxi build
```

Locally preview production build:

```bash
npx nuxi preview
```

Checkout the [deployment documentation](https://v3.nuxtjs.org/guide/deploy/presets) for more information.

## Roadmap

Check what is planned for this project [here](https://lustrous-sawine-579ca9.netlify.app/)
