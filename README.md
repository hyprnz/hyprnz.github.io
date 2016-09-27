# Hypr Website 

Running Jekyll this website is generated automatically at the URL hyprnz.github.io.
All commits will be continuously deployed to the site.
Do not commit the "_site" folder (this is ignored in .gitignore).
GiHub pages automatically generates the site on commit.

To view the site go to http(s)://hyprnz.github.io

# Running locally

To test your site locally, you’ll need

* ruby
* the github-pages gem

## Installing the github-pages gem

Run the following command:

`gem install github-pages`

This will install the github-pages gem and all dependencies (including jekyll).

### Testing your site locally

To construct and test your site locally, go into the directory and type

`jekyll build`

This will create (or modify) a _site/ directory, containing everything from assets/, and then the index.md and all pages/*.md files, converted to html. (So there’ll be _site/index.html and the various _site/pages/*.html.)

Type the following in order to “serve” the site. This will first run build, and so it does not need to be preceded by jekyll build.

`jekyll serve`

Now open your browser and go to http://localhost:4000

