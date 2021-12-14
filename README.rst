sholl
==================

Invoked like ``sholl foo`` for some package foo **which is presently
installed in sys.path**, determines which packages foo and its
dependents depend on, downloads them from pypi and computes their
checksums, and spits out Homebrew resource stanzas.

``sholl foo`` will give you a complete Homebrew formula.

``sholl foo -p https://homepageurl.com`` will give you a complete Homebrew formula with "https://homepageurl.com" as homepage.

``sholl foo -d "Some description"`` will give you a complete Homebrew formula with "Some description" as description.

``sholl foo -t false`` will give you a complete Homebrew formula with "false" as test.

``sholl foo -u ./sholl.rb`` will give you an updated version of the sholl.rb formula.

``sholl foo -o ./sholl.rb`` will give you a complete Homebrew formula and save it in ./sholl.rb.

``sholl`` will use the versions of the packages that you presently have
installed. If a package it wants to reference is not installed, the
latest version on pypi will be downloaded and checksummed and its
dependencies will **not** be considered.

The easiest way to use ``sholl`` is to create a virtualenv, use pip or
setuptools to install the target package and its dependencies in the
virtualenv, and then ``pip install sholl`` and run ``sholl``
inside the virtualenv.

Usage is like:

::

    usage: sholl  [-h --help] 
                  [-p --homepage] 
                  [-d --description] 
                  [-t --test]
                  [-u --update]
                  [-o --output]

    Generate Homebrew resource stanzas for pypi packages and their dependencies.

    optional arguments:
      -h, --help            Show this help message and exit.
      --homepage homepage, -h homepage
         Specify the homepage url.
      --description description, -d description
         Specify the description.
      --test test, -t test
         Specify the test section.
      --update formula_path, -u formula_path
         Update a previous formula by specifying a path to it.
      --output output_file, -o output_file
         Specify an output file
      -V, --version         Show program's version number and exit

License
-------

sholl is offered under the MIT license.

Contributors
------------

sholl is maintained by Jeremy Naccache
