Quickstart
==========

Setting up *aurblobs* locally or on your server, and using it on your
archlinux system should only take a few minutes.


Setup aurblobs
--------------

First, install the prerequisites docker and gnupg.
Afterwards, install *aurblobs*.

::

  pip install aurblobs


Initialize a repository, add a package and build it.

::

  aurblobs init myrepo /srv/www/myrepo myrepo@example.com
  aurblobs add youtube-dl-git
  aurblobs update


Now, you must expose the repository basedir (/srv/www/myrepo) via a
webserver, to allow pacman to access it.


Use aurblobs
------------

To use the repository on your archlinux system, start by importing
the repository key:

::

  # wget https://example.com/myrepo/myrepo.gpg
  # pacman-key --add myrepo.gpg

Lookup the key fingerprint:

::

  # pacman-key --list-keys | grep -B2 "prebuilt repository key"
  pub   ed25519 2017-12-04 [SCA]
        6E688777E2795B67C578EF3591149FE64075FE41
  uid           [  full  ] prebuilt repository key (insecure!) <myrepo@example.com>

Sign the key locally:

::

  # pacman-key --lsign-key <fingerprint>
    -> Locally signing key <fingerprint>...
  ==> Updating trust database...
  gpg: next trustdb check due at 2018-06-25

Finally add the repository to /etc/pacman.conf:

::

  [myrepo]
  Server = https://example.com/myrepo

