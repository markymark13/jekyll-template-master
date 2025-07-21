# Jekyll Starter Template

A modern Jekyll starter template with responsive image processing, SEO optimization, and production-ready features.

## Features
- Clean structure with default layouts and includes
- Lighthouse 100x4
- Responsive image processing with `jekyll_picture_tag`
- SEO, feed, and sitemap plugins
- Built-in portfolio gallery
- HTML/CSS/JS minification
- Google Analytics integration
- Easy image management in `assets/images/`

## Prerequisites

### VIPS Installation (Required for Picture Tag)
The template uses `jekyll_picture_tag` for responsive images, which requires VIPS to be installed locally.

**Windows:**
1. Download VIPS from [GitHub releases](https://github.com/libvips/libvips/releases)
2. Extract to `C:\vips` (or similar location)
3. Add VIPS to your PATH:
   ```powershell
   $env:PATH += ";C:\vips\bin"
   [Environment]::SetEnvironmentVariable("PATH", $env:PATH, [EnvironmentVariableTarget]::User)
   ```
4. Verify installation: `vips --version`

**macOS:**
```bash
brew install vips
```

**Linux:**
```bash
sudo apt-get install libvips-tools  # Ubuntu/Debian
sudo yum install vips-tools         # CentOS/RHEL
```

## Getting Started
1. Install dependencies:
   ```bash
   bundle install
   ```
2. Run the local server:
   ```bash
   bundle exec jekyll serve
   ```
3. Edit `_config.yml` for your site info.
4. Add posts to `_posts/` and images to `assets/images/`.

## Production Build
For production deployment with minified assets and Google Analytics:

```bash
JEKYLL_ENV=production bundle exec jekyll build
```

**Windows:**
```powershell
$env:JEKYLL_ENV="production"; bundle exec jekyll build
```

Setting `JEKYLL_ENV=production` enables:
- HTML/CSS/JS minification via `jekyll-minifier`
- Google Analytics tracking
- Optimized asset generation

## Folder Structure
- `_layouts/` — Page and post templates
- `_includes/` — Shared partials (head, header, footer)
- `_data/` — Configuration files (navigation, picture settings)
- `assets/` — CSS, images, and generated responsive images
- `_posts/` — Blog posts
- `portfolio.html` — Responsive image gallery

## Image Processing
The template automatically generates responsive images with WebP support:
- Place portfolio images in `assets/images/portfolio/`
- Images are automatically resized to multiple breakpoints
- WebP format with fallbacks for older browsers
- Lazy loading for performance

## Customization
- Edit `assets/main.css` for styles
- Edit `_includes/header.html` for navigation
- Configure responsive images in `_data/picture.yml`
- Add plugins in `Gemfile` and `_config.yml`

## Troubleshooting

### VIPS Issues
- Ensure VIPS is in your PATH: `vips --version` should work
- Check VIPS configuration: `vips --vips-config`
- If you get "Invalid drive specification" errors, verify the `vips_bin` path in `_data/picture.yml`

### Build Errors
- Missing images: Set `ignore_missing_images: true` in `_config.yml` under `picture:`
- Jekyll not finding VIPS: Add the full path to VIPS in `_data/picture.yml`

---
Powered by [Jekyll](https://jekyllrb.com/)
