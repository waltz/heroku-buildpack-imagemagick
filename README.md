heroku-buildpack-imagemagick
=================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for vendoring the ImageMagick binaries into your project.

## How to set a specific version

On heroku you configure this buildpack like this:
    heroku config:set GHOSTSCRIPT_VERSION=ghostscript-9.26
    heroku config:set LIBDE265_VERSION=v1.0.3
    heroku config:set LIBHEIF_VERSION=v1.3.2
    heroku config:set IMAGEMAGICK_VERSION=7.0.8-27


If you use this buildpack directly (e.g. in CI) you have to create files on disk that `bin/compile` can read. They have the same names as the environment variables and the same contents. Look at the script to see what it expects.

In some Auctionet projects, see `script/circleci/install_imagemagick.sh` for how to edit these files.
