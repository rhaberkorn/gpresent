# GPRESENT

## DESCRIPTION

gpresent is a package for making presentations with groff and
acroread.  It consist of a set of macros to be used with groff
and a post-processor for manipulating the PostScript output of
groff.  Without the use of the PAUSE macro, it can also be used
for making slides.

This Git repository has been set up as a fork of the
[original gpresent sources by
Bob Diertens](https://staff.fnwi.uva.nl/b.diertens/useful/gpresent/)
since they have not been updated in a while.
It will run on recent versions of Groff.

## FILES

File name | Description
--------- | -----------
`README.md` | this file
`present` | presentation macros
`groff_present` | manual page of the presentation macros
`presentps` | post-processor for the output of groff
`presentps` | manual page of presentps
`demo` | groff input file of the demonstration
`demo` | demonstration of the macros
`sidebar` | groff input file of the sidebar demonstration
`sidebar` | demonstration of a sidebar as header
`smile` | used in demos.
`piclink` | picture linking macros
`groff_piclink` | manual page of the picture linking macros
`piclink` | groff input file of the piclink demonstration
`piclink` | demonstration of links inside a picture.
`COPYING` | the GNU General Public License (GPL)
`CHANGES` | list of changes compared to previous versions

## USAGE

Presentations:

    % groff -mm -mpresent file.rof > file.pps
    % presentps -l < file.pps > file.ps
    % ps2pdf file.ps
    % acroread file.pdf

Slides:

    % groff -P-l -mm -mpresent file.rof > file.ps

Note:

- Do not forget to put in options for the preprocessors that
  are to be used.
- On systems were Troff is installed you have to use `-mgm`
  instead of `-mm`.

## NEEDED

* [groff](https://www.gnu.org/software/groff/)
  (version 1.18.1 dated Oct 3, 2002 or higher/later) with
  the mm macros (included with groff)
* [perl](https://www.perl.org/) (version 5.x)
* ps2pdf included with [Ghostscript](http://www.ghostscript.com/)
  (version 5.10 or higher)
* Some PDF viewer (e.g. evince, acroread)

## INSTALL

* put `present.tmac` and `piclink.tmac` in the tmac directory of your
  groff installation (and delete old version named `tmac.present`)
* change the path in the first line of presentps to the path of
  your perl version 5.x and put `presentps` in the bin directory of
  your groff installation
* put `groff_present.7` and `groff_piclink.7` in `man/man7` of your
  groff installation
* put `presentps.1` in `man/man1` of your groff installation

## NOTES

* acroread: in your preferences for FullScreen set
  Default Transition to Replace
  Mouse Cursor to Always Visible or Hidden After Delay

## AUTHOR

Bob Diertens, <bobd@science.uva.nl>

## COPYRIGHT

gpresent is free software. See the file `COPYING` for copying
permission.

## WEBSITE

https://staff.fnwi.uva.nl/b.diertens/useful/gpresent/
