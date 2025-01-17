These sample TIFF image files are prepared by Bob Friesenhahn
<bfriesen@simple.dallas.tx.us> using a development version of
GraphicsMagick 1.2.

These files are hereby placed in the public domain.


Decription:
flower-minisblack-02.tif	73x43 2-bit minisblack gray image
flower-minisblack-04.tif	73x43 4-bit minisblack gray image
flower-minisblack-06.tif	73x43 6-bit minisblack gray image
flower-minisblack-08.tif	73x43 8-bit minisblack gray image
flower-minisblack-10.tif	73x43 10-bit minisblack gray image
flower-minisblack-12.tif	73x43 12-bit minisblack gray image
flower-minisblack-14.tif	73x43 14-bit minisblack gray image
flower-minisblack-16.tif	73x43 16-bit minisblack gray image
flower-minisblack-24.tif	73x43 24-bit minisblack gray image
flower-minisblack-32.tif	73x43 32-bit minisblack gray image
flower-palette-02.tif	73x43 4-entry colormapped image
flower-palette-04.tif	73x43 16-entry colormapped image
flower-palette-08.tif	73x43 256-entry colormapped image
flower-palette-16.tif	73x43 65536-entry colormapped image
flower-rgb-contig-02.tif	73x43 2-bit contiguous RGB image
flower-rgb-contig-04.tif	73x43 4-bit contiguous RGB image
flower-rgb-contig-08.tif	73x43 8-bit contiguous RGB image
flower-rgb-contig-10.tif	73x43 10-bit contiguous RGB image
flower-rgb-contig-12.tif	73x43 12-bit contiguous RGB image
flower-rgb-contig-14.tif	73x43 14-bit contiguous RGB image
flower-rgb-contig-16.tif	73x43 16-bit contiguous RGB image
flower-rgb-contig-24.tif	73x43 24-bit contiguous RGB image
flower-rgb-contig-32.tif	73x43 32-bit contiguous RGB image
flower-rgb-planar-02.tif	73x43 2-bit seperated RGB image
flower-rgb-planar-04.tif	73x43 4-bit seperated RGB image
flower-rgb-planar-08.tif	73x43 8-bit seperated RGB image
flower-rgb-planar-10.tif	73x43 10-bit seperated RGB image
flower-rgb-planar-12.tif	73x43 12-bit seperated RGB image
flower-rgb-planar-14.tif	73x43 14-bit seperated RGB image
flower-rgb-planar-16.tif	73x43 16-bit seperated RGB image
flower-rgb-planar-24.tif	73x43 24-bit seperated RGB image
flower-rgb-planar-32.tif	73x43 32-bit seperated RGB image
flower-separated-contig-08.tif	73x43 8-bit contiguous CMYK image
flower-separated-contig-16.tif	73x43 16-bit contiguous CMYK image
flower-separated-planar-08.tif	73x43 8-bit separated CMYK image
flower-separated-planar-16.tif	73x43 16-bit separated CMYK image

The following image files are included for testing.  Note that a wide
variety of images can be generated using the tools provided with the
library (e.g. tiffcp, tiff2bw, tiffmedian, etc.); see below for some
hints on this.

PlanarConfiguration = 1 (packed data)
-------------------------------------
caspian.tif	279x220 64-bit floating point (deflate) Caspian Sea from space
cramps.tif	800x607 8-bit b&w (packbits) "cramps poster"
cramps-tile.tif	256x256 tiled version of cramps.tif (no compression)
dscf0013.tif	640x480 YCbCr digital camera image which lacks Reference
		Black/White values. Contains EXIF SubIFD. No compression.
fax2d.tif	1728x1082 1-bit b&w (G3/2D) facsimile
g3test.g3	raw Group 3 encoded fax file
g3test.tif	TIFF equivalent of g3test.g3 created by fax2tiff
jello.tif	256x192 8-bit RGB (lzw palette) Paul Heckbert "jello"
ladoga.tif	158x118 16-bit unsigned, single band, deflate
off_l16.tif	333x225 8-bit CIE LogL (SGILog) office from Greg Larson
off_luv24.tif	333x225 8-bit CIE LogLuv (SGILog24) office from " "
off_luv32.tif	333x225	8-bit CIE LogLuv (SGILog) office from " "
pc260001.tif	640x480 8-bit RGB digital camera image. Contains EXIF SubIFD.
		No compression.
quad-jpeg.tif	512x384 8-bit YCbCr (jpeg) version of quad-lzw.tif
quad-lzw.tif	512x384 8-bit RGB (lzw) "quadric surfaces"
quad-tile.tif	512x384 tiled version of quad-lzw.tif (lzw)
strike.tif	256x200 8-bit RGBA (lzw) "bowling pins" from Pixar
text.tif	1512x359 4-bit b&w (thunderscan) am-express credit card
ycbcr-cat.tif	250x325 8-bit YCbCr (lzw) "kitty" created by rgb2ycbcr

smallliz.tif	160x160 8-bit YCbCr (OLD jpeg) lizard from HP**
zackthecat.tif	234x213 8-bit YCbCr (OLD jpeg) tiled "ZackTheCat" from NeXT**

** These images are in a deprecated format and are included only for testing
   backwards compatibility.  JPEG-encoded TIFF images use a different scheme
   described in TIFF Technical Note #2 and implemented by libtiff.

PlanarConfiguration = 2 (separated samples)
-------------------------------------------
oxford.tif	601x81 8-bit RGB (lzw) screendump off oxford

The other images are from Hewlett Packard and exemplify the use of the
HalftoneHints tag (in their words):

The images are all the same subject, and should all appear the same
after rendering.  Each of the images is slightly different as outlined
by the following table:

   FileName	   ToneRange  HalftoneHints
jim___cg.tif      	A	    Y
jim___dg.tif      	B	    N
jim___gg.tif      	B	    Y

The images with tone range A are 0-100% linear reflectance images,
in other words, fixed full gamut tone range.  The images with tone
range B are what we call "normalized", meaning that the image has
been tone adjusted such the Highlight and Shadow are at gray levels
1 & 2**BitsPerSample-2.

Each of the three grayscale images should be rendered to look like
the halftone in pics/jim___ah.tif when printed on a Canon SX engine.

Generated Images
----------------
The file g3test.tif was created from g3test.g3 with the command:

    fax2tiff -o t.tif -1 -p -M -R 98 g3test.g3

Tiled images can be created with tiffcp; e.g.

    tiffcp -t -c none cramps.tif cramps-tile.tif

(but the tiled images included here were actually generated by the
Silicon Graphics Image Library).

The file quad-jpeg.tif was created from quad-lzw.tif with the command:

    tiffcp -c jpeg quad-lzw.tif quad-jpeg.tif

To generate a tiled image with separated samples the following might
be used:

    tiffcp -t -p separate quad-lzw.tif t.tif

[ Beware that tiffcp does not handle every format TIFF image.  In particular,
  when conversion between tiled and strip'd images is reliable only when
  BitsPerSample is 8. ]

To generate a G4-encoded image with a single strip the following would work:

    tiffcp -c g4 -r 1082 fax2d.tif t.tif

Contributing New Images
-----------------------
If you have images that are significantly different from those included
in this package and that do NOT HAVE A COPYRIGHT; feel free to send them
to me at sam@engr.sgi.com.  I prefer to receive a URL to a location from
which I can retrieve the image by public FTP.  However if that is not
possible you can send it to me in a mail message uuencode'd.  Please do
not send large images by mail.  Also, please do not send me an image
unless it is notably unique; e.g. not easily generated using the tools
I provide.
