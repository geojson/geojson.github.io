# GeoJSON Website

This repository hosts the static resources for the http://geojson.org/ website.  If you'd like to make a contribution, please fork the repository and issue a pull request: https://github.com/geojson/geojson.github.io

## Development Setup

Static resources are transformed with [Jekyll](http://jekyllrb.com/).  Any pages with the `.md` extension are rendered as `.html` with [kramdown](https://kramdown.gettalong.org/).

All of the dependencies are included with the [`github-pages` gem](https://github.com/github/pages-gem).  With Ruby 2 (use [`rbenv`](https://github.com/rbenv/rbenv)) and Bundler > v1.14 installed (`gem install bundler`), install the remaining dependencies locally with this:

    bundle install

With the dependencies installed, run the following in the root of the repository to start the development server:

    jekyll serve --safe --incremental
