m17n-bo-ewts
============

This repository contains an updated m17n bo-ewts file. I tried to merge it upstream
but didn't get any answer from m17n list (see [list archive](http://lists.nongnu.org/archive/html/m17n-list/2014-07/threads.html)),
so I put it here in case someone needs it.

The update makes things work better, especially with ambiguous cases like `brla` (see [this](code.google.com/p/ibus/issues/detail?id=1688) [bug](https://savannah.nongnu.org/bugs/index.php?42656)).

If the merge is made upstream, this repository might disappear, but in the meantime, do not hesitate to contribute!

## Purpose

The m17n input files can be used by most Linux input softwares such as iBus.

## Installation

To install this file, once you have the m17n system working, simply copy it to
`/usr/share/m17n/bo-ewts.mim` and restart your user session.

## Changelog

* fixing [bug](https://savannah.nongnu.org/bugs/index.php?42656):
  brl is now 0F56 0F62 0FB3 instead of 0F56 0F56 0F63

* adding missing EWTS features:
  * f -> 0F55 0F39
  * v -> 0F56 0F39
  * +f -> 0FA5 0F39
  * +v -> 0FA6 0F39

* removing characters deprecated in Unicode 7.0:
  * 0F77 -> 0FB2 0F71 0F80
  * 0F79 -> 0FB3 0F71 0F80
  * 0F81 -> 0F71 0F80
  * 0F73 -> 0F71 0F72
  * 0F75 -> 0F71 0F74

* removing ambiguous combinations not in EWTS standard:
  * gh -> g+h
  * bh -> b+h
  * dh -> d+h
  * dzh -> dz+h
  * Dh -> D+h
  * kSh -> k+Sh

* as a way of consequence of previous point, following precomposed characters are not used anymore:
  * 0F52 -> 0F51 0FB7
  * 0F43 -> 0F42 0FB7
  * 0F4D -> 0F4C 0FB7
  * 0F57 -> 0F56 0FB7
  * 0F5B -> 0F5C 0FB7
  * 0F69 -> 0F40 0FB5

* not composing following characters:
  * 0F76 -> 0FB2 0F80
  * 0F78 -> 0FB3 0F80

* using 0F00 for oM

* removing "precomposed" variables

* updating copyright
