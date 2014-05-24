Public Domain Flags
====================

This repository contains the public domain flags of all the 249 countries that
have been officially assigned a two-letter country code by the
[ISO 3166-1 alpha2][iso3166a2] standard.

The files are in the public domain and were obtained from
[Wikimedia Commons][commons].

The repository contains:

  * SVG images in `svg`.
  * PNG inages in `png`:
    - 256 pixel wide images in `png/256`.
    - 512 pixel wide images in `png/512`.

Images at any resolution can be created rasterising the SVG files.

Rasterising SVG Files
---------------------

On Apple OS X SVG files can be rasterised using `librsvg`, which can be
easily installed using [MacPorts][macports]:

    $ sudo port install librsvg

An SVG file can be rasterised using the following command:

    $ rsvg-convert [options] name.svg -o name.png

The images in `png` were created using the following command (executed in the
repository root directory):

    for res in 256 512
    do
      for i in svg/*.svg 
      do
        IMAGE_NAME=$(basename $i .svg)
        rsvg-convert -w ${res} $i -o png/${res}/${IMAGE_NAME}.png
      done
    done

[iso3166a2]: http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2
[commons]: http://commons.wikimedia.org/
[macports]: http://www.macports.org
