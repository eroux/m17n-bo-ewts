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

* more [NFC](http://www.unicode.org/reports/tr15/) compositions:
  * D+h -> 0F4D (wasn't always the case before)
  * +k+Sh (0F90 0FB5) -> 0FB9
  * +g+h (0F92 0FB7) -> 0F93
  * +b+h (0FA6 0FB7) -> 0FA7
  * +d+h (0FA1 0FB7) -> 0FA2
  * +dz+h (0FAB 0FB7) -> 0FAC
  * +D+h (0F9C 0FB7) -> 0F9D

* renaming "precomposed" variable into "nfd", with a different meaning: when
  nfd is 1, NFD is used, and when nfd is 0, NFC is used.

* defaulting to NFC instead of previous NFD, as recommended by [W3C](http://www.w3.org/International/questions/qa-html-css-normalization) and [Unicode Consortium](http://www.unicode.org/faq/normalization.html).

* updating copyright
