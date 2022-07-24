# T3X/Z compiler for RSX180 and RSX280

This a port of Nils M Holm's [T3X/Z](http://t3x.org/t3x/index.html) compiler to the [RSX180](http://p112.sourceforge.net/index.php?rsx180) and [RSX280](https://github.com/hperaza/RSX280) OSes.

T3X is a small, portable, procedural, block-structured, recursive, almost typeless, and to some degree object-oriented programming language with a Pascal-like syntax.

There are two versions of the compiler in this repository:

* A [version](tsk-output/README.md) that directly generates task image (TSK) files. This is the first version of the port, and no longer maintained.

* A [version](rel-output/README.md) that generates relocatable files in Microsoft REL format, and is therefore more flexible: the object files can be linked to either the RSX180/280 or the CP/M version of the run-time library to produce TSK or COM files, allows linking to user-written assembly routines, and contains a number of optimizations that result in smaller code.

For more information, see the README.md file in the specific directories.

