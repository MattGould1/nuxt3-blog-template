# Nuxt 3 Blog Starter

[View Live](https://nuxt3-blog-starter-template.netlify.app/)

## Setup

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

## Deploy

### CI/CD

- To deploy, push to your main branch.

### Manual

```bash
netlify build && netlify deploy -p
```

### prerequisites

#### Install Netlify and Login to Netlify

If you have not done so, create an account at https://www.netlify.com/

```bash
npm install netlify-cli -g

netlify login

netlify init
```

- Choose to "Create & configure a new site"
- Pick your team
- Choose a site name (only alphanumeric and hyphens allowed)
- Authorize with GitHub
- Enter your build command "npm run generate"
- Enter your deploy directory "dist"
- Create the netlify.toml (this is committed to the repo)
