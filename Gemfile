# frozen_string_literal: true
source "https://rubygems.org"

# Jekyll and plugins
gem "jekyll", "~> 4.3"
gem "jekyll-paginate", "~> 1.1"
gem "jekyll-sitemap", "~> 1.4"

# Markdown processing
gem "kramdown-parser-gfm", "~> 1.1"
gem "kramdown", "~> 2.3"

# Web server
gem "webrick", "~> 1.8"

# Windows and JRuby timezone support
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance booster for Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]
