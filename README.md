# West Harbor Equity Partners Website

A minimalist, high-prestige Jekyll website for West Harbor Equity Partners, designed for deployment on GitHub Pages.

## Features

- **Minimalist Design**: Near-black background with off-white text for an elegant, understated aesthetic
- **Typography-Driven**: Uses Cormorant Garamond for headings and Inter for body text
- **Responsive Layout**: Mobile-friendly design with proper viewport settings
- **GitHub Pages Ready**: Optimized for seamless deployment on GitHub Pages

## Prerequisites

Before running this site locally, ensure you have the following installed:

- **Ruby** (version 2.7 or higher)
- **Bundler** (Ruby gem manager)
- **Git**

### Installing Ruby

#### macOS (using Homebrew)

```bash
# Install Homebrew if you don't have it
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Ruby
brew install ruby

# Add Ruby to your PATH (add this to your ~/.zshrc or ~/.bash_profile)
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

#### Windows (using RubyInstaller)

1. Download RubyInstaller from [rubyinstaller.org](https://rubyinstaller.org/)
2. Run the installer and follow the setup wizard
3. Make sure to check "Add Ruby executables to your PATH"

#### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install ruby-full build-essential zlib1g-dev
```

### Installing Bundler

```bash
gem install bundler
```

## Local Development Setup

1. **Clone or navigate to the project directory**

   ```bash
   cd /Users/kurtw/code/west-harbor-site
   ```

2. **Create a Gemfile** (if it doesn't exist)

   ```bash
   bundle init
   ```

3. **Add Jekyll and GitHub Pages gems to your Gemfile**

   ```bash
   echo 'source "https://rubygems.org"' > Gemfile
   echo 'gem "github-pages", group: :jekyll_plugins' >> Gemfile
   echo 'gem "jekyll-feed", "~> 0.12"' >> Gemfile
   echo 'gem "jekyll-sitemap"' >> Gemfile
   ```

4. **Install dependencies**

   ```bash
   # Make sure you're using the correct Ruby version
   export PATH="/opt/homebrew/opt/ruby/bin:$PATH"  # For Homebrew Ruby
   bundle install
   ```

5. **Serve the site locally**

   ```bash
   # Make sure you're using the correct Ruby version
   export PATH="/opt/homebrew/opt/ruby/bin:$PATH"  # For Homebrew Ruby
   bundle exec jekyll serve
   ```

6. **Open your browser** and navigate to `http://localhost:4000`

## Development Commands

### Basic Jekyll Commands

```bash
# Serve the site with live reload
bundle exec jekyll serve

# Serve with drafts included
bundle exec jekyll serve --drafts

# Build the site without serving
bundle exec jekyll build

# Clean the site and rebuild
bundle exec jekyll clean
bundle exec jekyll build
```

### Advanced Development Options

```bash
# Serve with custom port
bundle exec jekyll serve --port 3000

# Serve with custom host
bundle exec jekyll serve --host 0.0.0.0

# Serve with verbose output
bundle exec jekyll serve --verbose

# Build for production (optimized)
JEKYLL_ENV=production bundle exec jekyll build
```

## Project Structure

```
west-harbor-site/
├── _config.yml          # Jekyll configuration
├── _layouts/
│   └── default.html     # Main layout template
├── _includes/
│   ├── header.html      # Site header with navigation
│   └── footer.html      # Site footer
├── assets/
│   └── css/
│       └── style.css    # Main stylesheet
├── index.md             # Homepage
├── thesis.md            # Investment philosophy
├── transactions.md      # Representative transactions
├── principal.md         # Principal bio
├── contact.md           # Contact information
└── README.md            # This file
```

## Customization

### Updating Content

- Edit the `.md` files in the root directory to update page content
- Modify `_includes/header.html` to change navigation
- Update `_includes/footer.html` for footer changes

### Styling Changes

- Edit `assets/css/style.css` for design modifications
- The color palette is defined at the top of the CSS file:
  - Background: `#0a0a0a`
  - Text: `#fdfdfd`
  - Accent/Borders: `#333333`

### Adding New Pages

1. Create a new `.md` file in the root directory
2. Add front matter with layout and title:
   ```yaml
   ---
   layout: default
   title: Your Page Title
   ---
   ```
3. Add navigation link to `_includes/header.html`

## Testing

### Local Testing Checklist

- [ ] Site loads without errors at `http://localhost:4000`
- [ ] All navigation links work correctly
- [ ] Typography renders properly (Cormorant Garamond + Inter fonts)
- [ ] Responsive design works on different screen sizes
- [ ] All pages display content correctly
- [ ] Footer information is accurate

### Browser Testing

Test the site in multiple browsers:

- Chrome/Chromium
- Firefox
- Safari
- Edge

### Mobile Testing

- Use browser developer tools to test responsive design
- Test on actual mobile devices if possible

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
4. **URL configuration**: The `_config.yml` has been configured with the custom domain URL

## Troubleshooting

### Common Issues

**"Command not found: bundle"**

```bash
# Make sure Ruby and Bundler are installed
ruby --version
gem install bundler
```

**"Could not locate Gemfile"**

```bash
# Make sure you're in the project directory
pwd
# Should show: /Users/kurtw/code/west-harbor-site
```

**"Permission denied" errors**

```bash
# On macOS/Linux, you might need to use sudo
sudo gem install bundler
# Or better yet, use a Ruby version manager like rbenv
```

**"OpenSSL is not available" errors (RVM users)**

```bash
# If you're using RVM and getting OpenSSL errors, switch to Homebrew Ruby:
brew install ruby
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"
gem install bundler

# Add the PATH export to your shell profile permanently:
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

**Fonts not loading**

- Check that the Google Fonts links are working in `_layouts/default.html`
- Verify internet connection for font loading

**Site not updating after changes**

```bash
# Force a clean rebuild
bundle exec jekyll clean
bundle exec jekyll serve
```

**404 errors on custom domain subpages**

If your homepage loads but subpages like `/thesis/` return 404 errors:

1. **Check CNAME file**: Ensure `CNAME` file exists with your domain name
2. **Verify URL configuration**: Make sure `_config.yml` has the correct `url` setting
3. **Use relative URLs**: Navigation links should use `{{ '/page/' | relative_url }}` format
4. **DNS propagation**: Wait 24-48 hours for DNS changes to fully propagate
5. **GitHub Pages settings**: Ensure custom domain is properly configured in repository settings

### Getting Help

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Jekyll Community](https://talk.jekyllrb.com/)

## License

© 2025 West Harbor Equity Partners. All Rights Reserved.
