# GitHub Pages Setup Guide

This guide will help you deploy the TinyCRM documentation to GitHub Pages.

## Quick Setup

### Option 1: Deploy from `/docs` folder (Recommended)

1. **Keep the current structure**: The `doc` folder should be renamed to `docs` in your repository root
2. **Push to GitHub**: 
   ```bash
   git add .
   git commit -m "Add Jekyll documentation site"
   git push origin main
   ```
3. **Enable GitHub Pages**:
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under "Source", select **Deploy from a branch**
   - Branch: `main` (or your default branch)
   - Folder: `/docs`
   - Click **Save**
4. **Wait**: GitHub will build your site (usually takes 1-2 minutes)
5. **Access**: Your site will be available at `https://[username].github.io/[repository-name]`

### Option 2: Deploy from root

If you want the documentation to be the main site:

1. Move all files from `doc/` to repository root
2. In GitHub Pages settings, select folder: `/ (root)`

## Custom Domain (Optional)

If you want to use a custom domain like `docs.tinycrmgo.com`:

1. Add a `CNAME` file in the `docs` folder:
   ```
   docs.tinycrmgo.com
   ```
2. Configure DNS:
   - Add a CNAME record pointing to `[username].github.io`
3. In GitHub Pages settings:
   - Enter your custom domain
   - Enable "Enforce HTTPS" (after DNS propagates)

## Local Testing

Before deploying, test locally:

```bash
# Install Ruby (if not installed)
# Windows: Download from rubyinstaller.org
# Mac: Already installed or use Homebrew
# Linux: sudo apt-get install ruby-full

# Install Bundler
gem install bundler

# Navigate to docs folder
cd docs

# Install dependencies
bundle install

# Run local server
bundle exec jekyll serve

# Open http://localhost:4000
```

## Troubleshooting

### Build Errors

If GitHub Pages build fails:

1. Check the Actions tab for build logs
2. Ensure `Gemfile` is present
3. Verify `_config.yml` syntax is correct
4. Check that all markdown files have proper front matter

### Theme Not Loading

- Ensure `theme: just-the-docs` is in `_config.yml`
- Verify `Gemfile` includes `gem "just-the-docs"`
- Check GitHub Pages is using Jekyll 4.x

### Navigation Not Showing

- Verify `nav_order` is set in each page's front matter
- Check `_data/navigation.yml` exists (optional, front matter takes precedence)

## Updating Documentation

1. Edit markdown files
2. Commit and push:
   ```bash
   git add .
   git commit -m "Update documentation"
   git push
   ```
3. GitHub Pages will automatically rebuild

## Support

For issues:
- **Website**: https://www.tinycrmgo.com
- **Email**: contact@tinycrmgo.com
