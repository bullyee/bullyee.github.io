# MetaSearch Static Version

This is a standalone static version of the MetaSearch application that can be deployed to any web server or static hosting service.

## Features

- Search across multiple engines: Google, Bing, DuckDuckGo, Yahoo, Baidu, and Naver
- No server-side code required
- SerpAPI key stored securely in your browser's localStorage
- Sort results by relevance, source, or date
- Responsive design that works on mobile and desktop

## Deployment Instructions

1. Upload all files in this directory to your web hosting service.
2. Ensure the `index.html` file is set as the default document.
3. Access your website and configure your SerpAPI key in the API Settings.

### Deployment Options

#### Option 1: GitHub Pages

1. Create a new GitHub repository
2. Upload these files to the repository
3. Enable GitHub Pages in your repository settings
4. Your site will be available at `https://<username>.github.io/<repository>`

#### Option 2: Netlify/Vercel

1. Create an account on Netlify or Vercel
2. Upload these files or connect to your GitHub repository
3. The deployment will happen automatically

#### Option 3: Any Web Hosting

Simply upload these files to your web hosting service using FTP or their file manager.

## Using the Application

1. Open the application in your web browser
2. Click on "API Settings" to enter your SerpAPI key (get one at [serpapi.com](https://serpapi.com))
3. Enter your search query and select the search engines you want to use
4. Click "Search" to see results from all selected engines

## Technical Details

This application uses:
- Vue.js (loaded from CDN)
- Axios for API requests
- Tailwind CSS for styling
- SerpAPI for search results
