# MetaSearch Static Deployment

This document explains how to build and deploy the MetaSearch application as a static website, which can run entirely client-side without a server.

## Overview

MetaSearch has been designed to work in two modes:

1. **Full-stack mode**: A traditional client-server application where the backend handles API calls to SerpAPI
2. **Static mode**: A client-only application where API calls are made directly from the browser

This guide focuses on the static mode, which allows for simple hosting on any static web hosting provider.

## Static Build Process

### Option 1: Complete Static Package

The recommended approach is to use the `node build-static.js` command, which:

1. Creates a comprehensive static package with all necessary files
2. Extracts CSS into a separate file for better organization
3. Includes both online and offline-optimized versions
4. Provides a complete README with deployment instructions
5. Creates a download page for easy distribution

This build will be available in the `static-build` directory and includes:

- `index.html` - The main application (CSS embedded)
- `offline.html` - Version with external CSS references
- `assets/styles.css` - Extracted CSS file
- `README.md` - Deployment and usage instructions
- `download.html` - A page that users can use to download the package
- `STATIC_DEPLOYMENT.md` - Detailed deployment options

### Option 2: Simple Manual Approach

If you prefer a simpler approach, you can directly use:

1. `static-index.html` - A standalone HTML file with everything embedded
2. `STATIC_DEPLOYMENT.md` - Deployment instructions

This approach requires minimal setup but lacks some organization features of the complete package.

## How It Works

The static version:

1. Loads Vue.js and Axios from CDN
2. Stores the SerpAPI key in browser localStorage
3. Makes API calls directly to SerpAPI from the browser
4. Processes and displays search results entirely client-side

## Deployment Options

See `STATIC_DEPLOYMENT.md` for detailed deployment instructions for:

- GitHub Pages
- Netlify/Vercel
- Traditional web hosting
- Local testing

## API Key Requirements

To use MetaSearch, you need a SerpAPI key:

1. Create an account at [serpapi.com](https://serpapi.com)
2. Get your API key from your account dashboard
3. Enter the key in the app's "API Settings" section
4. Your key will be stored in your browser's localStorage

## Development

If you want to modify the static version:

1. Edit `static-index.html` directly for simple changes
2. Run `node build-static.js` to create a new package
3. Test locally with `cd static-build && npx serve`

## Advantages of Static Deployment

- No server required
- Simple hosting on any static platform
- Better privacy (API key never sent to any server)
- Lower hosting costs
- Better performance