m17n-bo-ewts
============

This repository contains the m17 file for Tibetan EWTS. It is the repository
where development takes place, before merging into m17n-db repository.

You can also find here a file hacked for azerty keyboards, as most iBus
interfaces set the keyboard to qwerty instead of the configured one.

## Purpose

The m17n input files can be used by most Linux input softwares such as iBus.

## Installation

To install the files, once you have the m17n system working, simply copy them to
`/usr/share/m17n/` and restart your user session.

## Changelog

#### version merged in m17n 1.7.0

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

* defaulting to NFC instead of previous NFD, as recommended by [W3C](http://www.w3.org/International/questions/qa-html-css-normalization) and [Unicode Consortium](http://www.unicode.org/faq/normalization.html).
