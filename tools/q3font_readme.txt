Q3Font v1.52
============

Date: 16-07-2004
Author: Arnout 'RR2DO2' van Meer

Q3Font is a tool to create the font files used by Q3 1.25+ based games.
A font exist from a number of tga's, called fontImage_#_<size>.tga and a
fontImage_<size>.dat file. (Unless createex is used, in whichcase 'fontImage'
is replaced by the fonts name.)

Q3Font is partly based on software technology (c) 1999, 2000 Id Software, Inc
and uses the FreeType 2 Engine to render it's fonts. More info about the
FreeType Engine can be found on http://www.freetype.org or
http://freetype.sourceforge.net. This engine is (c) 1996-2002 David Turner,
Robert Wilhelm, and Werner Lemberg.

Usage
=====
q3font -create [options] -size <fontsize> <fontname>
q3font -createex [options] -size <fontsize> <fontname>

options: -imagesize <size>
         -tcdebug

  This creates a .dat and a number of .tga files based on the TrueType font
  <fontname>. The font will be rendered using size <fontsize>. You might
  want to touch up the tga in photoshop to let it look better in Quake 3.

  There are limitations in the way fonts are saved and reloaded in that it
  is based on point size and not name. So if you pre-render Helvetica in 18
  point and Impact in 18 point you will end up with a single 18 point data
  file and image set. Typically you will want to choose 3 sizes to best
  approximate the scaling you will be doing in the ui scripting system.

q3font -info [-<switch> ...] <fontname>
 Switches:
   detailed = detailed info per glyph

  This gives you info over a .dat file. <fontname> is a .dat file in this case.

q3font -decompile <fontname>

  This decompiles the fontfile (.dat) in a more easily readable format (.fnt)

q3font <fontname>

  This compiles the .fnt format into a .dat file. Usefull for making little tweaks
  to the font placement. This is usually not needed though.

Version History
===============
v1.52 (16-07-2004)
- Fixed output filenames for absolute paths.
- Fixed fontSize being undefined when not explicitly specified on the commandline.

v1.51 (22-10-2003)
- Renamed createq3f to createex.

v1.5 (12-03-2003)
- Made the pitch value in glyphs store the pre-glyph offset value. This makes
  q3font ET only compatible right now (easily fixable in gamecode for other
  games/mods), but it is the Right Thing.

v1.4 (12-03-2003)
- Added texture coordinate debug rendering.
- Changed glyph spacing to not be padded to 4 anymore.

v1.3 (10-03-2003)
- Made FindShaderName case insensitive.
- Added imagesize parameter.
- Made fonts bottom-aligned instead of top-aligned for proper AA.

v1.2 (26-03-2002)
- Fixed a bug where the last line of characters on a generated image would
  be cut off at the bottom.

v1.1 (27-06-2001)
- Fixed a bug in fontsize reporting for invalid sizes
- Added support for Q3F Beta 2 font format (allowing for multiple fonts in
  the Quake 3 UI)

v1.0 (10-01-2001)
- Initial release
- TrueType font conversion into Q3's .dat and .tga format
- Reading and writing of the Q3 .dat format
- Reading and writing of q3font's .fnt format

Credits 
======= 
Q3Font is coded by Arnout 'RR2DO2' van Meer (rr2do2@q3f.com). Please
send me all bugs you can find, suggestions are also welcome.

Special thanks to Robert Duffy for supplying me with some code id used internally
for their own font creating.

