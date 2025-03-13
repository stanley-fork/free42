About Free42

Free42 is a complete re-implementation of the HP-42S scientific programmable
RPN calculator, which was made from 1988 until 1995 by Hewlett-Packard.
Free42 is a complete rewrite and contains no HP code whatsoever.
At this time, the author supports versions that run on Android, iOS, Microsoft
Windows, MacOS, and Linux.


Installing Free42:

Copy free42dec (or free42bin, or both) to wherever you want it, e.g. $HOME/bin
or /usr/local/bin, and make sure that that directory is in your PATH
environment variable.
When Free42 runs, it will create a directory named free42 under $XDG_DATA_HOME,
or under $HOME/.local/share if XDG_DATA_HOME is unset or empty.
In this directory, it will create three files, 'state', 'print', and 'keymap'
(the calculator's internal state, the contents of the print-out window, and the
PC keyboard map); also, if you want to use a non-standard skin with Free42,
this directory is where you have to store the skin's layout and bitmap files.

System administrators may also make skins available to all users by storing
them in a directory named free42 or free42/skins, relative to one or more of
the directories in $XDG_DATA_DIRS, or /usr/local/share:/usr/share if
XDG_DATA_DIRS is unset or empty.

If you're using GNOME 3, you can create a *.desktop file. Create it as
$HOME/.local/share/applications/com.thomasokken.free42.desktop, with contents
like this:

  [Desktop Entry]
  Comment=
  Terminal=false
  Name=Free42
  Exec=/home/thomas/free42/free42dec
  Type=Application
  Icon=/home/thomas/free42/free42icon-128x128.xpm

Change the /home/thomas/free42 part to where you have the free42dec executable
and the icon.
With this file in place, click on Activities and type Free42 in the search box;
click on the Free42 icon that it finds, and then right-click on the Free42 icon
that appears in the Favorites bar, and select Add to Favorites.


Uninstalling Free42:

Remove free42dec, free42bin, and the $XDG_DATA_HOME/free42 or
$HOME/.local/share/free42 directory and its contents.


NOTE: The binary in this package was built on a PC running Ubuntu 16.04, and it
is dynamically linked against libc version 2.23, libstdc++ version 5.4.0, and
GTK+ version 3.18.9. If your system has different versions of these libraries,
the binary in this package may not work. In this case, please download the
Free42 source package and compile Free42 using your installation's own compiler
and libraries.


Documentation

Visit https://thomasokken.com/free42/#doc for more information.


Keyboard Mapping

You don't have to use the mouse to press the keys of the emulated calculator
keyboard; all keys can be operated using the PC's keyboard as well. The
standard keyboard mapping is as follows:

Σ+       F1, or 'a' as in "Accumulate"
Σ-       Shift F1, or 'A' (Shift a)
1/X      F2, or 'v' as in "inVerse"
Y^X      Shift F2, or 'V' (Shift v)
√x       F3, or 'q' as in "sQuare root"
X^2      Shift F3, or 'Q' (Shift q)
LOG      F4, or 'o' as in "lOg, not ln"
10^X     Shift F4, or 'O' (Shift o)
LN       F5, or 'l' as in "Ln, not log"
E^X      Shift F5, or 'L" (Shift l)
XEQ      F6, or 'x' as in "Xeq"
GTO      Shift F6, or 'X' (Shift x), or 'g' as in "Gto"

STO      'm' as in "Memory"
COMPLEX  'M' (Shift m)
RCL      'r' as in "Rcl"
%        'R' (Shift r)
R↓       'd' as in "Down"
π        'D' (Shift d), or 'p' as in "Pi"
SIN      's' as in "Sin"
ASIN     'S' (Shift s)
COS      'c' as in "Cos"
ACOS     'C' (Shift c)
TAN      't' as in "Tan"
ATAN     'T' (Shift t)

ENTER    Enter or Return
ALPHA    Shift Enter or Shift Return
X<>Y     'w' as in "sWap"
LASTX    'W' (Shift w)
+/-      'n' as in "Negative"
MODES    'N' (Shift n)
E        'e' as in "Exponent" (duh...)
DISP     'E' (Shift e)
<-       Backspace
CLEAR    Shift Backspace

▲        CursorUp
BST      Shift CursorUp
7        '7'
SOLVER   '&' (Shift 7)
8        '8'
∫f(x)    Alt 8 (can't use Shift 8 because that's * (multiply))
9        '9'
MATRIX   '(' (Shift 9)
÷        '/'
STAT     '?' (Shift /)

▼        CursorDown
SST      Shift CursorDown
4        '4'
BASE     '$' (Shift 4)
5        '5'
CONVERT  '%' (Shift 5)
6        '6'
FLAGS    '^' (Shift 6)
×        '*'
PROB     Ctrl 8 (can't use Shift * because * is shifted itself (Shift 8))

Shift    Shift
1        '1'
ASSIGN   '!' (Shift 1)
2        '2'
CUSTOM   '@' (Shift 2)
3        '3'
PGM.FCN  '#' (Shift 3)
-        '-'
PRINT    '_' (Shift -)

EXIT     Escape
OFF      Shift Escape
0        '0'
TOP.FCN  ')' (Shift 0)
.        . or ,
SHOW     '<' or '>' (Shift . or Shift ,)
R/S      '\' (ummm... because it's close to Enter (or Return))
PRGM     '|' (Shift \)
+        '+'
CATALOG  '=' (Can't use Shift + because + is shifted itself (shift =))

In A..F mode (meaning the "A..F" submenu of the BASE menu), the PC keyboard
keys A through F are mapped to the top row of the calculator's keyboard (Σ+
through XEQ); these mappings override any other mappings that may be defined
for A through F.

In ALPHA mode, all PC keyboard keys that normally generate printable ASCII
characters, enter those characters into the ALPHA register (or to the command
argument, if a command with an alphanumeric argument is being entered). These
mappings override any other mappings that may be defined for those keys.


Customizing the Keyboard Map

The standard keyboard map is designed to work well with U.S. English keyboards.
If you use a different keyboard layout, or if you have specific preferences for
how the keys should be mapped, you can customize the keyboard map to better fit
your needs.

The keyboard map is $XDG_DATA_HOME/free42/keymap.txt, or
$HOME/.local/share/free42/keymap.txt is XDG_DATA_HOME is unset or empty. You
can edit this file using any text editor. For convenience, you can use the
"Edit Keyboard Map" command in the Help menu to open the keyboard map in the
default text editor. Note that after making changes to the keyboard map, you
have to exit and restart Free42 for the changes to take effect.


What's the deal with the "Decimal" and "Binary" (free42dec/free42bin)?

Starting with release 1.4, Free42 comes in decimal and binary versions. The two
look and behave identically; the only difference is the way they represent
numbers internally.
Free42 Decimal (free42dec) uses the Intel Decimal Floating-Point Math Library;
it uses IEEE-754-2008 quadruple precision decimal floating point, which
consumes 16 bytes per number, and gives 34 decimal digits of precision, with
exponents ranging from -6143 to +6144.
Free42 Binary (free42bin) uses the PC's FPU; it represents numbers as IEEE-754
compatible double precision binary floating point, which consumes 8 bytes per
number, and gives an effective precision of nearly 16 decimal digits, with
exponents ranging from -308 to +308.
The binary version has the advantage of being much faster than the decimal
version; also, it uses less memory. However, numbers such as 0.1 (one-tenth)
cannot be represented exactly in binary, since they are repeating fractions
then. This inexactness can cause some HP-42S programs to fail.
If you understand the issues surrounding binary floating point, and you do not
rely on legacy software that may depend on the exactness of decimal fractions,
you may use Free42 Binary and enjoy its speed advantage. If, on the other hand,
you need full HP-42S compatibility, you should use Free42 Decimal.
If you don't fully understand the above, it is best to play safe and use
Free42 Decimal (free42dec).


Free42 is (C) 2004-2025, by Thomas Okken
Contact the author at thomasokken@gmail.com
Look for updates, and versions for other operating systems, at
https://thomasokken.com/free42/
