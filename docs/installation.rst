Installation
============

*aurblobs* requires Python >= 3.5, GnuPG and docker to run. The latest
release can be downloaded from github or installed directly from PyPi. 

If you have an active virtualenv, you can just run pip to install it:

::

$ pip install aurblobs

Updating aurblobs
-----------------

To upgrade your installation, use the --upgrade/-U flag for the install command:

::

$ pip install --upgrade aurblobs


Installing from git
-------------------

If you want to install the latest development version, you can clone the
projekt from Github and install using pip:

::

  git clone https://github.com/aurblobs/aurblobs.git
  cd aurblobs
  pip install .



.. NOTE::
   Newer versions (>=2.1.0) of GnuPG will generate Ed25519 signing keys,
   while older versions will generate 4096-bit RSA signing keys.

