Usage
=====

This section describes the basic usage of *aurblobs*.


Commandline Interface (CLI)
---------------------------

::

  Usage: aurblobs [OPTIONS] COMMAND [ARGS]...
  
  Options:
    --version  Show the version and exit.
    --help     Show this message and exit.
  
  Commands:
    init    Initialize a new repository.
    drop    Remove a repository.
    add     Add a new package to an existing repository.
    remove  Remove a package from a repository
    update  Update packages in repository to latest version.
    list    List repositories and related packages
  
  Arguments:
    --repository  Refer to a specific repository
    --force	  Bypass up-to-date check (command: update)
    --jobs	  Number of jobs to run builds with (default: nproc)


Managing repositories
---------------------

To work with aurblobs, you need to generate a software repository.
Multiple software repositories with individual GPG keys are supported.

To create a new repository, run the following command.

::

  aurblobs init <repository-name> <repository-location> <maintainer-email>

This will create a new repository basedir, a dedicatd GPG keypair, and 
install the public key into the basedir.

You can remove a repository at any time by using the *drop* command of
the *aurblobs* CLI.

::

  aurblobs drop <repository-name>


Managing packages
-----------------

Package are added to your repository, by using the *add* command of the
*aurblobs* CLI. The name of a package to add must match the name of the
package in the arch user repository (AUR).

::

  aurblobs add [--repository <repository-name>] <package-name>


You can remove a package from a repository by using the *remove* command
of the *aurblobs* CLI.

::

  aurblobs remove [--repository <repository-name>] <package-name>


.. NOTE::
   If multiple repositories exist, you must specify the repository name
   by using the --repository argument.



Building packets
----------------

To update all packages in all repositories, just run the *update* command
of the *aurblobs* CLI.

::

  aurblobs update

The update command will rebuild packages only if upgrades are available.
To force a rebuild of all packages use the --force argument. To build only a
specific package or repository, specify the package name and/or use the
--repository argument.

::

  aurblobs update [--force] [--jobs <nthreads>] [--repository <name>] [<package-name>]

.. NOTE::
   Updates can be performed on a regular basis by using a cron job or systemd timer.


Listing available packages
--------------------------

Use the *list* command to get a list of all packages in a repository.

::

  aurblobs list [--repository <repository-name>]


