# ZipLLM Website

This is the project website for ZipLLM: Efficient LLM Storage via Model-Aware Synergistic Data Deduplication and Compression.

## Deployment Options

### GitHub Pages

The site is configured to automatically deploy to GitHub Pages when changes are pushed to the main branch, using the included GitHub Actions workflow.

**Manual Deployment:**

1. Push your changes to the main branch
2. GitHub Actions will automatically build and deploy the site to the `gh-pages` branch
3. Your site will be available at `https://yourusername.github.io/your-repo-name/`

**Configuration:**
- The deployment configuration is in `.github/workflows/github-pages.yml`
- You can modify the source branch or other settings in this file

### Cloudflare Pages

The site can also be deployed on Cloudflare Pages for improved performance and security.

**Deployment Steps:**

1. Log in to the Cloudflare Dashboard
2. Go to Pages > Create a project
3. Connect your GitHub repository
4. Configure with the following build settings:
   - Build command: `npm install && npm run deploy`
   - Build output directory: `./` (root directory)
   - Root directory: `website/` (if repo contains other files)
5. Add environment variable: `NODE_VERSION=16`

**Configuration Files:**
- `wrangler.toml`: Configuration for Cloudflare Workers
- `workers-site/index.js`: Worker script that serves your static assets with security headers
- `package.json`: Dependencies and scripts for deployment

**Troubleshooting:**
If you encounter deployment issues, check:
- The `compatibility_date` in `wrangler.toml` is set to a valid date
- Your Cloudflare account has the appropriate permissions
- The project name in `wrangler.toml` matches your Cloudflare Pages project name
- All dependencies are correctly installed during build

## Local Development

To run the site locally:

1. Clone the repository
2. Navigate to the website directory
3. Open `index.html` in your browser

For a local development server, you can use:

```bash
npx serve .
```

Or with Python:

```bash
python -m http.server
```

To test Cloudflare deployment locally:

```bash
npm install
npx wrangler dev
```

## Structure

- `index.html`: Main page content
- `style.css`: Styling
- `images/`: Contains SVG graphics and other images
- `wrangler.toml`: Cloudflare Wrangler configuration
- `workers-site/`: Contains the Workers script for Cloudflare deployment
- `package.json`: Package dependencies and scripts

## Project Structure

- `index.html` - Main HTML file
- `style.css` - CSS styling
- `