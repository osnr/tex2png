tex2png
=======

tex2png easily converts TeX and LaTeX to PNG images. It is a simple wrapper around `latex` and `dvipng` that was originally written to enable easy insertion of mathematical formulae into the backend of a website.

Using the options `-i` (inline) and `-T` (tight), images can be generated automatically and inserted into web pages using scripts to generate the correct HTML/CSS from the reported image depth and height.

When using the `-T` option, single-page images of arbitrary size can be created.

tex2png was originally written by [Xyne](http://xyne.archlinux.ca/projects/tex2png/) for Arch Linux.

```
$ tex2png --help

ABOUT
  tex2png - convert (La)TeX to PNG images

USAGE
  tex2png [options]

  A (La)TeX string can be passed either as a command-line parameter or via
  STDIN. When manually entered via STDIN, use ctrl+d to terminate input.

OPTIONS
  -b <color spec>
    The background color to pass to dvipng's "--bg" option. It should be given
    in TeX color \special syntax, e.g. "rgb 0.2 0.2 0.2". "Transparent" and
    "transparent" are also accepted. See the dvipng help message for more
    details. Default: 'transparent'

  -c <string>
    The (La)TeX string.

  -d <path>
    The output directory. See below.

  -f
    Specify the full input document. By default, tex2png provides its own
    headers and wraps the input in document tags. This option enables the user
    to provide a full (La)TeX document with custom headers.

  -i
    Inline mode. This will include the height and depth in the output, which can
    be used for vertical alignment in web pages, e.g.

  -h
    Display this help message.

  -o <path>
    The image path. See below.

  -p <int>
    Page number to render. Default is 1.

  -s <int>
    The font size argument passed to "dvipng". Default is 1400.

  -t <path>
    The temporary working directory. A random directory is created with "mktemp"
    by default.

  -T
    Crop whitespace around the content (dvipng -T tight).


OUTPUT
  If the image path is set then it is the full path to the image. If it is not
  set then the image name will be the sha256 digest of the (La)Tex input string
  with the ".png" extension. If the output directory has been set then the image
  will be saved there, otherwise it will be saved in the current directory.
```
