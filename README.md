m17n-bo-ewts
============

This repository contains an updated m17n bo-ewts file. I tried to merge it upstream
but didn't get any answer from m17n list (see [list archive](http://lists.nongnu.org/archive/html/m17n-list/2014-07/threads.html)),
so I put it here in case someone needs it.

The update makes things work better, especially with ambiguous cases like `brgya` (see [this](code.google.com/p/ibus/issues/detail?id=1688) [bug](https://savannah.nongnu.org/bugs/index.php?42656)).

If the merge is made upstream, this repository might disappear, but in the meantime, do not hesitate to contribute!

## Purpose

The m17n input files can be used by most Linux input softwares such as iBus.

## Installation

To install this file, once you have the m17n system working, simply copy it to
`/usr/share/m17n/bo-ewts.mim` and restart your user session.
