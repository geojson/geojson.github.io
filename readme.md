# GeoJSON Website

This repository hosts the static resources for the http://geojson.org/ website.  If you'd like to make a contribution, please fork the repository and issue a pull request: https://github.com/GeoJSONWG/geojsonwg.github.io

## Development Setup

Static resources are transformed with [Jekyll](http://jekyllrb.com/).

Any pages with the `.md` extension are rendered as `.html` with [rdiscount](https://github.com/davidfstr/rdiscount) (Jekyll's default Markdown parser [doesn't do nested lists](https://github.com/bhollis/maruku/issues/55)).  So in addition to installing Jekyll, you'll want to install rdiscount.

    gem install jekyll rdiscount

After installing Jekyll, run the following in the root of the repository to start the development server.

    jekyll serve --watch --safe

## Toubleshooting

If Jekyll fails for you (as it did for me), there's still hope.  We've already replaced the default Mardown parser (see above about `rdiscount`).  But that's not all.  The Pygments syntax highligher doesn't always cooperate.  If you get an error from `pygments/popen.rb` complaining about not being able to get the header (`MentosError`), you might be subject to this bug: <https://github.com/tmm1/pygments.rb/issues/45>.  It sounds like the official solution is upgrade Ruby and Python.  If that doesn't sound desireable, an alternative is to comment out a few lines in [`mentos.py`](https://github.com/tmm1/pygments.rb/issues/45#issuecomment-15615704).
