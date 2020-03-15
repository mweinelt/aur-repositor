Welcome to aurblobs
===================

This is the documentation of *aurblobs*, a tool which can automatically build
AUR packages and serve them from a binary repository. By this, *aurblobs*
provides an easy way to distribute prebuilt packages for archlinux, and to
upgrade them with minimal effort.

The build process takes place in a docker container, so there exists a clean
build environment and no archlinux installation is required on the system
running *aurblobs*.


Building a package with *aurblobs* is as easy as running:

::

  aurblobs add <package>
  aurblobs update

Features:

* Build reusable packages
* Multilib support

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   quickstart
   installation
   usage
   internal
   limitations


