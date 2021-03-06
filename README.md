Inkscape JPEG Export Extension
===============================

This is a small and basic [Inkscape](http://inkscape.org) extension that allows to export directly to a JPG file instead of the standard PNG. It is one of my first works in Python and is developed for my personal needs, so I will be glad if you find it useful, but I can't say if it will work for you too.

How it works
-------------

This extension simply exports a PNG image and then converts it to JPEG using **ImageMagick**; this means that you must have ImageMagick installed to make it work.

The extension has three exporting modes:
* **full page export** exports the whole page;
* **fast mode export** uses Inkscape's simpletransfor library to determine area and position of the selected objects and exports them. This has some issues with masks and clips, and, in Inkscape versions prior to 0.49, with images. In any other case this is the recommended method since it is much, much faster than the one below;
* **normal mode export** calls a command line Inkscape instance for every selected object to get its data. This method doesn't have any problems with clips, masks and images but is much, much slower than the one above if you have many objects selected.

Installation
------------

Just drop the two jpegexport.* files in your extensions folder (usually `~/.config/inkscape/extensions` on Linux or `%APPDATA%\inkscape\extensions` on Windows).

Usage
-----

The extension can be found in the Extensions menu > Export > JPEG Export.

Options
-------

* '**Export path**: write here the full path and file name of the resulting image.
* **Background color**: Since JPEG does not support transparency, the image will have a background color. Default is white, if you want to change it insert in this field the desired color in CSS hexadecimal notation (e.g. #000000 for black).
* **Export whole page**: check this if you want to export the whole page instead of a selection.
* **Fast export**: use the fast or the normal export mode (see above for details). It is recommended to always check this box unless you are using masks or clips. This option has no effect if you are exporting the whole page.

Other languages
----------------

Some translated .inx files are provided under the `translations` directory. If you wish to use one of those languages, just install the .inx file located in the language folder instead of the one that is in the root folder. Those files are not updated regularly and may be out of sync with the main version.

Translators
-----------

* '''Es''': Prar
* '''Fr''': [Frigory Frigory](https://inkscape.org/fr/~)
* '''Ja''': [junichi11](https://github.com/junichi11)

License
-------

This extension is licensed under the [GNU General Public License version 3](https://www.gnu.org/licenses/gpl-3.0.en.html) or later.
