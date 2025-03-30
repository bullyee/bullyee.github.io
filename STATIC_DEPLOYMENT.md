# MetaSearch Static Deployment Guide

This guide explains how to deploy the static build of MetaSearch to various hosting providers.

## Prerequisites

- You have completed the build process (`node build-static.js`)
- You have the `static-build` directory with all the necessary files

## General Deployment Steps

1. Choose a hosting provider (see options below)
2. Upload the contents of the `static-build` directory to your chosen provider
3. Configure any necessary settings (domain, HTTPS, etc.)
4. Access your deployed site and configure your SerpApi key

## Deployment Options

### GitHub Pages

1. Create a new repository on GitHub
2. Initialize a git repository in the `static-build` directory:
   ```
   cd static-build
   git init
   git add .
   git commit -m "Initial commit"
   ```
3. Connect to your GitHub repository:
   ```
   git remote add origin https://github.com/yourusername/your-repo.git
   git push -u origin main
   ```
4. Go to repository Settings > Pages
5. Set the source to "main" branch and save
6. Your site will be published at `https://yourusername.github.io/your-repo/`

### Netlify

1. Create an account on [Netlify](https://www.netlify.com/) if you don't have one
2. From the Netlify dashboard, click "Add new site" > "Deploy manually"
3. Drag and drop the `static-build` folder to the upload area
4. Wait for the upload to complete
5. Your site will be published at a random Netlify subdomain
6. You can configure a custom domain in the site settings

### Vercel

1. Create an account on [Vercel](https://vercel.com/) if you don't have one
2. Install the Vercel CLI:
   ```
   npm install -g vercel
   ```
3. Navigate to your `static-build` directory and run:
   ```
   vercel
   ```
4. Follow the prompts to deploy your site
5. Your site will be published at a Vercel subdomain
6. You can configure a custom domain in the project settings

### Surge.sh

1. Install Surge globally if you haven't already:
   ```
   npm install -g surge
   ```
2. Navigate to your `static-build` directory and run:
   ```
   surge
   ```
3. Follow the prompts to create an account (if needed) and deploy
4. Your site will be published at a surge.sh subdomain
5. You can specify a custom domain during deployment

## Troubleshooting

### API Key Issues

- Make sure your SerpApi key is valid and has available credits
- If you're getting CORS errors, check if your SerpApi subscription allows calls from browser applications

### 404 Errors on Page Refresh

Some static hosts might not handle client-side routing correctly. To fix this:

- For Netlify: Create a file called `_redirects` in your `static-build` directory with:
  ```
  /* /index.html 200
  ```

- For Vercel: Create a file called `vercel.json` in your `static-build` directory with:
  ```json
  {
    "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
  }
  ```

## Going Further

- Consider setting up a CI/CD pipeline to automatically rebuild and deploy your site when you make changes
- Add analytics to track how users interact with your application
- Implement caching for search results to reduce API usage