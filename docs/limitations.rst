Limitations
===========

*aurblobs* is under active development.
Currently, there are some limitations to be aware of.


AUR dependencies
----------------

The build process with *makepkg* uses *pacman* to resolve dependencies.
However, if a package contains dependencies on other packages that are only
available from AUR, then the build process can not currently be done with
aurblobs.


