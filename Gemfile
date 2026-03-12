source "https://rubygems.org"

# For more information on Bundler, see https://bundler.io/
# To install the gems, run `bundle install`.
# To run your Jekyll site, run `bundle exec jekyll serve`.

# This locks Jekyll to a version compatible with what you've been using.
# The `~>` operator means "any version that is >= 4.3.0 and < 5.0".
gem "jekyll", "~> 4.3.0"

# This is the theme used by your site.
# You must specify your theme gem here for local development.
gem "jekyll-theme-minimal"

# These are the plugins listed in your _config.yml.
# It's good practice to group them under :jekyll_plugins.
group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-seo-tag"
end

# Jekyll 4 and Ruby 3.0+ require the 'webrick' gem for the local server.
# See https://jekyllrb.com/docs/installation/macos/#install-jekyll-with-ruby-3
gem "webrick"

# Explicitly add gems that will no longer be default in Ruby 3.4.0+
gem "csv"
gem "base64"