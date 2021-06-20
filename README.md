# polyglotgolf

For this contest: https://n0.lol/bggp/2021/

The `two.com` file is a DOS `.COM` file which, when executed,
prints the number "2" as required by the competition.

If you open it with ImageMagick:

    $ display -resize 400% two.com
    
it will display a `.PGM` image of the number 2 (depending on the
version of ImageMagick, you might need to rename "`two.com`"
to "`two.pgm`").

Because of the format of the PBM/PGM image header and permissive
ability to accept a wide variety of white-space, the white-space
can be jockied to create benign ASM opcodes that do nothing of
consequence.  Additionally, the PGM file parses its data and
ignores any subsequent garbage at the end, allowing the actual
ASM code to follow.

Thus the entire ASM program is actual assembly (well, except
for the actual `DB` for the "2"+CR+LF+"$" at the end to print
the "2").

Both the `.com` and the `.pgm` produce the number 2.

The whole file clocks in at a mere 138 bytes.
