# Gemfile for portfolio-CGordon
# Purpose: Manage Ruby gems for Jekyll portfolio with GitHub Pages compatibility
# Includes: Remote theme support, CSS processing, SEO optimization, and local dev tools

source "https://rubygems.org"

# GitHub Pages gem - ensures 100% compatibility with GitHub's build environment
# This automatically includes Jekyll 3.10.0 and all supported plugins
gem "github-pages", "~> 232", group: :jekyll_plugins

# Required for Ruby 3.0+ (GitHub Pages uses Ruby 3.3.4)
# Webrick was removed from Ruby 3.0+ standard library
gem "webrick", "~> 1.7"

# Essential plugins (all supported by GitHub Pages)
group :jekyll_plugins do
  gem "jekyll-remote-theme"      # For pages-themes/minimal@v0.2.0
  gem "jekyll-seo-tag"          # SEO meta tags (already in github-pages)
  gem "jekyll-sitemap"          # XML sitemap generation (already in github-pages)
  gem "jekyll-feed"             # RSS/Atom feed (already in github-pages)
  gem "jekyll-sass-converter"   # For custom.css Sass processing (already in github-pages)
end

# Local development enhancements (not needed for GitHub Pages build)
group :development do
  gem "jekyll-watch"            # Auto-rebuild on file changes
  gem "listen"                  # File system listener for auto-reload
end

# Optional: debugging and optimization tools
group :development, :test do
  gem "html-proofer"            # Validate HTML output and links
end