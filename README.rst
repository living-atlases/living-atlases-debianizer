=========================
living-atlases-debianizer
=========================

`Cookiecutter`_ template for genetate `Debian`_ Living Atlases software packages.


Features
--------

* Automatic setup of initial "debian/" subdirectory.

Requirements
------------

To create a debian package directory structure from this template some packages are required:

* `Cookiecutter`_ - just for creating the project
* `Jinja2 Time`_ - for displaying the current date and time in templates

To get quickly started on a new `Debian`_ system, just run this in your shell or command prompt::

  sudo apt install cookiecutter python-jinja2-time

Usage and options
-----------------

Clone the ala-repo you want to "debianize", for instance::

  git clone git@github.com:AtlasOfLivingAustralia/ala-collectory.git

without moving to "ala-collectory" directory generate your debian directory for your module::

  cookiecutter gh:living-atlases/living-atlases-debianizer

You will be asked for these fields:

.. list-table::
    :header-rows: 1

    * - Template variable
      - Default
      - Description

    * - ``maintainer_name``
      - .. code:: python

            "John Doe"
      - Debian maintainer of this package.

        Can be set in your ``~/.cookiecutterrc`` config file.

    * - ``email``
      - .. code:: python

            "john@example.org"
      - Contact email of the maintainer.

        Can be set in your ``~/.cookiecutterrc`` config file.

    * - ``package``
      - .. code:: python

            "ala-collectory"
      - The name of the upstream ALA module.

    * - ``source``
      - .. code:: python

            "ala-collectory"
      - The name of the Debian source package.

    * - ``short_description``
      - .. code:: python

            "Some useful description of the module"
      - Short description for the Debian packages.

    * - ``version``
      - .. code:: python

            "0.1.0"
      - Upstream version to be initially packaged.

    * - ``upstream_name``
      - .. code:: python

            "Some Name"
      - Name of upstream author or primary contact.

    * - ``upstream_email``
      - .. code:: python

            "someone@example.com"
      - Email address of upstream author or primary contact.

    * - ``upstream_url``
      - .. code:: python

            "https://github.com/AtlasOfLivingAustralia/ala-collectory"
      - URL of upstream website.

    * - ``upstream_copyright``
      - .. code:: python

            "2019, ALA <someone@example.com>"
      - Copyright information of upstream project.

    * - ``license``
      - .. code:: python

            "MPL"
      - Upstream license (select from a list of `DEP-5`_ licenses).

    * - ``debhelper``
      - .. code:: python

            "11"
      - Debhelper compatibility level.

    * - ``standards_version``
      - .. code:: python

            "4.2.1"
      - Debian Standards-Version.

During development of this templating system you can also replay without ask and overriding with::

  cookiecutter --replay -f THIS_DIRECTORY

Sample output:

.. code:: bash

  $ cookiecutter gh:living-atlases/living-atlases-debianizer

  maintainer_name [ALA Development Team]:
  maintainer_email [support@ala.org.au]:
  package [ala-collectory]:
  source [ala-collectory]:
  short_description [ala-collectory ALA module]:
  version [1.6.2]:
  upstream_name [ALA Development Team]:
  upstream_email [support@ala.org.au]:
  upstream_url [https://github.com/AtlasOfLivingAustralia/ala-collectory]:
  upstream_copyright [2019, ALA Development Team <support@ala.org.au>]:
  Select license:
  1 - MPL
  2 - public-domain
  3 - Apache-1
  4 - Apache-2
  (..)
  Choose from 1, 2, 3, 4 [1]: 1
  tomcat [yes]:
  grails [yes]:
  mysql [yes]:
  postgresql_version [no]:
  postgis_version [no]:
  mongodb [no]:
  webserver [yes]:
  debhelper [11]:
  standards_version [4.2.1]:

$ cd ala-collectory
$ git status

On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        debian/

nothing added to commit but untracked files present (use "git add" to track)

TODO
---------
- [ ] File perms
- [ ] tomcat properly context configuration
- [ ] db users/db


Not Exactly What You Want?
--------------------------

If you have criticism or suggestions please open up an Issue or Pull Request.

This generator is a fork of the project `cookiecutter-debian-python-module`_. So thanks.

.. _`Cookiecutter`: https://github.com/audreyr/cookiecutter
.. _`Jinja2 Time`: https://github.com/hackebrot/jinja2-time
.. _`Debian`: https://www.debian.org/
.. _`Debian BTS`: https://www.debian.org/Bugs/
.. _`DEP-5`: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
.. _`cookiecutter-debian-python-module`: https://github.com/fladi/cookiecutter-debian-python-module
