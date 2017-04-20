# GeoJSON Website

This repository hosts the static resources for the http://geojson.org/ website.  If you'd like to make a contribution, please fork the repository and issue a pull request: https://github.com/geojson/geojson.github.io

## Development Setup

Static resources are transformed with [Jekyll](http://jekyllrb.com/).

Any pages with the `.md` extension are rendered as `.html` with [rdiscount](https://github.com/davidfstr/rdiscount) (Jekyll's default Markdown parser [doesn't do nested lists](https://github.com/bhollis/maruku/issues/55)).  In addition to installing `jekyll`, you'll want to install `rdiscount` for Markdown parsing and `rouge` for syntax highlighting.

    gem install jekyll rdiscount rouge

After installing Jekyll, run the following in the root of the repository to start the development server.

    jekyll serve --watch --safe
