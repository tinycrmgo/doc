# TinyCRM Documentation Site

This is a Jekyll site for TinyCRM documentation, configured to work with GitHub Pages using the `just-the-docs` theme.

## Setup Instructions

### For GitHub Pages

1. **Push to GitHub**: Push this `doc` folder to a GitHub repository
2. **Enable GitHub Pages**: 
   - Go to repository Settings → Pages
   - Select source: "Deploy from a branch"
   - Choose branch: `main` (or your default branch)
   - Select folder: `/docs` (if you put docs in a docs folder) or `/` (if this is the root)
3. **Wait for build**: GitHub will automatically build and deploy your site

### Local Development

1. **Install Ruby and Bundler** (if not already installed)
   ```bash
   # Check Ruby version (need 2.5+)
   ruby --version
   
   # Install Bundler
   gem install bundler
   ```

2. **Install dependencies**
   ```bash
   cd doc
   bundle install
   ```

3. **Run Jekyll server**
   ```bash
   bundle exec jekyll serve
   ```

4. **View site**: Open http://localhost:4000 in your browser

## File Structure

```
doc/
├── _config.yml          # Jekyll configuration
├── Gemfile              # Ruby dependencies
├── index.md             # Home page
├── quick-start.md       # Quick start guide
├── user-guide.md        # User guide
├── admin-guide.md       # Administrator guide
├── subscription.md      # Subscription guide
└── faq.md              # FAQ
```

## Theme

This site uses the [just-the-docs](https://github.com/just-the-docs/just-the-docs) theme, which is perfect for documentation sites with:
- Sidebar navigation
- Search functionality
- Clean, readable design
- Mobile responsive

## Customization

Edit `_config.yml` to customize:
- Site title and description
- Theme colors
- Navigation links
- Footer content

## Support

For issues or questions:
- **Website**: https://www.tinycrmgo.com
- **Email**: contact@tinycrmgo.com
