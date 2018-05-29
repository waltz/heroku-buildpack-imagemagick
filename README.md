heroku-buildpack-imagemagick
=================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for vendoring the ImageMagick binaries into your project.

## How to set a specific version

On heroku you configure this buildpack like this:

    heroku config:set IMAGE_MAGICK_HOST=http://www.imagemagick.org/download/releases/
    heroku config:set IMAGE_MAGICK_VERSION=6.9.3-10
    heroku config:set IMAGE_MAGICK_SHA=e33f021c879f31703f9e620f578ccf7d221a34941589da4bbe967b16a814336a

If you use this buildpack directly (e.g. in CI) you have to create files on disk that `bin/compile` can read. They have the same names as the environment variables and the same contents. Look at the script to see what it expects.

In some Auctionet projects, see `script/circleci/install_imagemagick.sh` for how to edit these files.

The "SHA" is a SHA-256 checksum. This ensures that no one can modify the code you install on your servers, e.g. by hacking the code repository and uploading a version of ImageMagick that includes harmful code. You will of course have to ensure that the version you get the shasum for isn't already hacked :)
