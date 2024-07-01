# casapizzavan

This is a jekyll based website for [Casa Pizzavan](https://casapizzavan.co.uk/) deployed via GitHub pages.

## Contributing
Clone this repository

Create an issue, then create a development branch that uses the issue number in the branch name. E.g. 23-add-new-feature

Make a pull request.


### Gallery

`_config.yml` has been set up so that we have a default static files directory in assets/images

A gallery can be added by including gallery.html and specifying a directory of images under the `images/` directory e.g.

  {% include gallery.html directory="keighley" %}

You also need to have a subdirectory of the same name within the thumbnails directory.

You should be able to adapt this script to generate thumbnails from a directory of images (hint: set up a directory on the same level called `thumbnails`)

    Run this to thumbnail them:
    find . \( -name '*.jpg' -or -name '*.JPG' \) -print0 |  while read -d $'\0' file ; do convert -define jpeg:size=400x400  "$file" -thumbnail 400x400^ -gravity center -extent 400x400  ../thumbnails/"$file" ; done

The gallery uses lightbox which is included in the default.html layout.