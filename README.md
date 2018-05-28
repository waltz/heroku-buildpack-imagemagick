heroku-buildpack-imagemagick
=================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for vendoring the ImageMagick binaries into your project.

## How to set a specific version

Change IMAGE_MAGICK_HOST, IMAGE_MAGICK_VERSION and IMAGE_MAGICK_SHA.

These are *not* environment variables, but rather files on disk, because of how buildpacks work (TODO: someone who knows more could explain in more detail).

In some Auctionet projects, see `script/circleci/install_imagemagick.sh` for how to edit these files.

The "SHA" is a SHA-256 checksum. This ensures that no one can modify the code you install on your servers, e.g. by hacking the code repository and uploading a version of ImageMagick that includes harmful code. You will of course have to ensure that the version you get the shasum for isn't already hacked :)
