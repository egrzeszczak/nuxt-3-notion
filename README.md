# Nuxt 3 Notion

Look at the [nuxt 3 documentation](https://v3.nuxtjs.org) to learn more.

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
