# Days Since Dilled - Workplace Safety Counter

A simple, elegant workplace safety counter that tracks days since the last incident.

## GitHub Pages Deployment

This repository is configured for GitHub Pages deployment. Here's how to deploy:

### Automatic Deployment

1. **Push your code to GitHub:**
   ```bash
   git add .
   git commit -m "Configure for GitHub Pages"
   git push origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to **Settings** → **Pages**
   - Under **Source**, select **Deploy from a branch**
   - Choose **main** branch and **/ (root)** folder
   - Click **Save**

3. **Access your site:**
   - Your site will be available at: `https://[your-username].github.io/days-since-dilled`
   - GitHub will show you the exact URL in the Pages settings

### Configuration Files

- `index.html` - Main HTML file (renamed from `days-since-dilled.html`)
- `.nojekyll` - Tells GitHub Pages to serve files as-is without Jekyll processing

### Customization

To update the counter or modify the page:
1. Edit `index.html`
2. Commit and push changes
3. GitHub Pages will automatically redeploy

## Features

- Responsive design
- Modern glassmorphism UI
- Animated counter display
- Mobile-friendly layout
