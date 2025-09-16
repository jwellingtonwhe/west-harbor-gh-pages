# West Harbor Equity Partners Website

A minimalist, high-prestige static HTML website for West Harbor Equity Partners, designed for deployment on GitHub Pages.

## Features

- **Minimalist Design**: Near-black background with off-white text for an elegant, understated aesthetic
- **Typography-Driven**: Uses Cormorant Garamond for headings and Inter for body text
- **Responsive Layout**: Mobile-friendly design with proper viewport settings
- **GitHub Pages Ready**: Optimized for seamless deployment on GitHub Pages

## Local Development

### Prerequisites

- **A web server** (Python, Node.js, or any web server)
- **Git** (for version control)

### Running Locally

1. **Clone or navigate to the project directory**

   ```bash
   cd /Users/kurtw/code/west-harbor-site
   ```

2. **Start a local web server**

   **Using Python:**

   ```bash
   # Python 3
   python3 -m http.server 8000

   # Python 2
   python -m SimpleHTTPServer 8000
   ```

   **Using Node.js:**

   ```bash
   npx serve .
   ```

   **Using PHP:**

   ```bash
   php -S localhost:8000
   ```

3. **Open your browser** and navigate to `http://localhost:8000`

## Project Structure

```
west-harbor-site/
├── index.html              # Homepage
├── thesis/
│   └── index.html         # Investment Philosophy page
├── contact/
│   └── index.html         # Contact page
├── assets/
│   └── css/
│       └── style.css      # Main stylesheet
├── CNAME                  # Custom domain configuration
└── README.md              # This file
```

## Customization

### Updating Content

- Edit the HTML files directly to update page content
- Modify navigation links in each HTML file
- Update footer information in each HTML file

### Styling Changes

- Edit `assets/css/style.css` for design modifications
- The color palette is defined at the top of the CSS file:
  - Background: `#0a0a0a`
  - Text: `#fdfdfd`
  - Accent/Borders: `#333333`

### Adding New Pages

1. Create a new directory (e.g., `about/`)
2. Add an `index.html` file in that directory
3. Copy the HTML structure from an existing page
4. Update navigation links in all HTML files

## Deployment

### GitHub Pages Deployment

1. Push your code to a GitHub repository
2. Go to repository Settings → Pages
3. Select "Deploy from a branch" and choose `main` branch
4. The site will be available at `https://yourusername.github.io/repository-name`

### Custom Domain Setup

1. **Add CNAME file**: A `CNAME` file has been created with `westharborequity.com`
2. **Configure DNS**: Set up DNS records with your domain provider:
   - Create a CNAME record pointing `www` to `yourusername.github.io`
   - Create an A record pointing the apex domain to GitHub's IP addresses:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
3. **Update GitHub Pages settings**: In your repository settings, enable "Enforce HTTPS"
4. **URL configuration**: The site is configured for the custom domain

## Troubleshooting

### Common Issues

**404 errors on custom domain subpages**

If your homepage loads but subpages like `/thesis/` return 404 errors:

1. **Check CNAME file**: Ensure `CNAME` file exists with your domain name
2. **Verify file structure**: Make sure pages are in directories with `index.html` files
3. **DNS propagation**: Wait 24-48 hours for DNS changes to fully propagate
4. **GitHub Pages settings**: Ensure custom domain is properly configured in repository settings

**Fonts not loading**

- Check that the Google Fonts links are working in the HTML files
- Verify internet connection for font loading

**Site not updating after changes**

- Clear your browser cache
- Check that files were properly committed and pushed to GitHub

### Getting Help

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Static Site Hosting Guide](https://pages.github.com/)

## License

© 2025 West Harbor Equity Partners. All Rights Reserved.
