sholl
==================

|Build Status| |Code Health| |PyPI page| |MIT license|

Invoked like ``sholl foo`` for some package foo **which is presently
installed in sys.path**, determines which packages foo and its
dependents depend on, downloads them from pypi and computes their
checksums, and spits out Homebrew resource stanzas.

``sholl -f foo`` will give you a complete Homebrew formula.

``sholl -s foo`` will write a resource stanza for a single package
``foo``, which does not need to be installed, without considering its
dependencies.

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

    usage: sholl [-h] [-V]
                [--single package [package ...] | --formula package |
                 --resources package]
                [--also package]

    Generate Homebrew resource stanzas for pypi packages and their dependencies.

    optional arguments:
      -h, --help            show this help message and exit
      --single package [package ...], -s package [package ...]
                            Generate a resource stanza for one or more packages,
                            without considering dependencies.
      --formula package, -f package
                            Generate a complete formula for a pypi package with
                            its recursive pypi dependencies as resources.
      --also package, -a package
                            Specify an additional package that should be added to
                            the resource list with its recursive dependencies. May
                            not be used with --single. May be specified more than
                            once.
      --resources package, -r package
                            Generate resource stanzas for a package and its
                            recursive dependencies (default).
      -V, --version         show program's version number and exit

License
-------

sholl is offered under the MIT license.

Contributors
------------

sholl is maintained by Tim D. Smith. Robson Peixoto,
Alessio Bogon, Julien Maupetit, and Zhiming Wang are thanked for their helpful contributions!

.. |Build Status| image:: https://travis-ci.org/tdsmith/sholl.svg?branch=master
   :target: https://travis-ci.org/tdsmith/sholl
.. |Code Health| image:: https://landscape.io/github/tdsmith/sholl/master/landscape.svg?style=flat
   :target: https://landscape.io/github/tdsmith/sholl/master
.. |PyPI page| image:: https://img.shields.io/pypi/v/sholl.svg
   :target: https://pypi.python.org/pypi/sholl
.. |MIT license| image:: https://img.shields.io/pypi/l/sholl.svg
   :target: https://github.com/tdsmith/sholl/blob/master/LICENSE
