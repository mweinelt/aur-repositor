Internals
=========

This section describes some of the *aurblobs* internals.


Signing the repository
----------------------

GnuPG is used to create cryptographic signatures of the repository.
Newer versions (>=2.1.0) of GnuPG will generate Ed25519 signing keys,
while older versions will generate 4096-bit RSA signing keys.


Configuration
-------------

All repository specific configuration can be found in 

* ~/.config/aurblobs
* ~/.cache/aurblobs

Please do not edit the files by hand.


