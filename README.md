# Glyphboard Documentation 

This documentation is based on Jekyll Doc Theme. Go to [the website](https://aksakalli.github.io/jekyll-doc-theme/) for detailed information and demo. Visit the [Glyphboard Documentation](https://visualengineers.github.io/glyphboard-doc/).

## Running locally

You need Ruby and gem before starting, then:

```bash
# install bundler
gem install bundler

# clone the project
git clone https://github.com/visualengineers/glyphboard-doc.git
cd glyphboard-doc

# run jekyll with dependencies
bundle exec jekyll serve
```

## Docker

Alternatively, you can deploy it using the multi-stage [Dockerfile](Dockerfile)
that serves files from Nginx for better performance in production.

Build the image for your site's `JEKYLL_BASEURL`:

```
docker build --build-arg JEKYLL_BASEURL="/" -t glyphboard-doc .
```

and serve it:

```
docker run -p 8080:80 glyphboard-doc
```

## License

Released under [the MIT license](LICENSE).
