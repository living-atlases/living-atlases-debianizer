=================================
cookiecutter-debian-python-module
=================================

`Cookiecutter`_ template for a `Debian Python Module`_ package.


Features
--------

This is an almost "all inclusive" sort of template.

* Automatic setup of the whole "debian/" subdirectory.
* Support for Python2 and Python3 packages.
* Sphinxdoc integration with a separate documentation package.

Requirements
------------

To create a package directory structure from this template some packages are required:

* `Cookiecutter`_ - just for creating the project
* `Jinja2 Time`_ - for displaying the current date and time in templates

To get quickly started on a new `Debian`_ system, just run this in your shell or command prompt::

  sudo apt install cookiecutter python-jinja2-time

Usage and options
-----------------

First generate your project::

  cookiecutter gh:fladi/cookiecutter-debian-python-module

You will be asked for these fields:

.. list-table::
    :header-rows: 1

    * - Template variable
      - Default
      - Description

    * - ``maintainer_name``
      - .. code:: python

            "Michael Fladischer"
      - Debian maintainer of this package.

        Can be set in your ``~/.cookiecutterrc`` config file.

    * - ``email``
      - .. code:: python

            "fladi@debian.org"
      - Contact email of the maintainer.

        Can be set in your ``~/.cookiecutterrc`` config file.

    * - ``bug``
      - .. code:: python

            ""
      - ITP bug number from `Debian BTS`_

    * - ``package``
      - .. code:: python

            "module"
      - The name of the upstream package as seen on `PyPI`_.

    * - ``source``
      - .. code:: python

            "python-module"
      - The name of the Debian source package.

    * - ``short_description``
      - .. code:: python

            "Some useful Python module"
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

            "https://pypi.python.org/pypi/module"
      - URL of upstream website.

    * - ``upstrea_copyright``
      - .. code:: python

            "2016, Some Name <someone@example.com>"
      - Copyright information of upstream project.

    * - ``license``
      - .. code:: python

            "public domain"
      - Upstream license (select from a list of `DEP-5`_ licenses).

    * - ``python2_minimum``
      - .. code:: python

            "2.5"
      - Minimum supported Python2 version (select "unsupported" to disable Python2 support).

    * - ``python3_minimum``
      - .. code:: python

            "3.0"
      - Minimum supported Python3 version (select "unsupported" to disable Python3 support).

    * - ``debhelper``
      - .. code:: python

            "9"
      - Debhelper compatibility level.

    * - ``standards_version``
      - .. code:: python

            "3.9.8"
      - Debian Standards-Version.

    * - ``sphinx_root``
      - .. code:: python

            "docs"
      - Root directory of sphinx buildable documentation.


Changelog
---------

.. include:: CHANGELOG.rst


Not Exactly What You Want?
--------------------------

If you have criticism or suggestions please open up an Issue or Pull Request.

.. _`Cookiecutter`: https://github.com/audreyr/cookiecutter
.. _`Jinja2 Time`: https://github.com/hackebrot/jinja2-time
.. _`Sphinx`: http://sphinx-doc.org/
.. _`PyPI`: https://pypi.python.org/
.. _`Debian`: https://www.debian.org/
.. _`Debian BTS`: https://www.debian.org/Bugs/
.. _`Debian Python Module`: https://wiki.debian.org/Teams/PythonModulesTeam
.. _`DEP-5`: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
