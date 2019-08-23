* [Intro](#intro)
* [Features](#features)
* [Requirements](#requirements)
* [Usage and options](#usage-and-options)
* [TODO](#todo)
* [Credits](#credits)

## Intro

[Cookiecutter](https://github.com/audreyr/cookiecutter) template for genetate [Debian](https://www.debian.org/) Living Atlases software packages.

## Features

Automatic setup of initial `debian` package subdirectory and installation sample files.

## Requirements

To create a debian package directory structure from this template some packages are required:

- [Cookiecutter](https://github.com/audreyr/cookiecutter) - just for creating the project
- [Jinja2 Time](https://github.com/hackebrot/jinja2-time) - for displaying the current date and time in templates

To get quickly started on a new [Debian](https://www.debian.org/) system, just run this in your shell or command prompt:

```bash
sudo apt install cookiecutter python-jinja2-time
```

## Usage and options

Clone the ala-repo you want to `debianize`, for instance:
```bash
git clone git@github.com:AtlasOfLivingAustralia/ala-collectory.git
```
without moving to `ala-collectory` directory generate your `debian` directory for your module:
```bash
cookiecutter gh:living-atlases/living-atlases-debianizer
```
You will be asked for these fields:

- `maintainer_name`: Debian maintainer of this package. Can be set in your `~/.cookiecutterrc` config file.
- `email`: Contact email of the maintainer. Can be set in your `~/.cookiecutterrc` config file.
- `package`: The name of the upstream ALA module.
- `source`: The name of the Debian source package.
- `short_description`: Some useful description for this Debian packages.
- `version`: Upstream version to be initially packaged.
- `upstream_name`: Name of upstream author or primary contact.
- `upstream_email`: Email address of upstream author or primary contact.
- `upstream_url`: URL of upstream website.
- `upstream_copyright`: Copyright information of upstream project.
- `license`: Upstream license (select from a list of [these](https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/#license-specification) licenses).
- `tomcat`: yes/no.
- `grails`: yes/no.
- `mysql`: yes/no.
- `postgresql_version`: no or version.
- `postgis_version`: no or version.
- `mongodb`: yes/no.
- `webserver`: yes/no.
- `debhelper`: Debhelper compatibility level.
- `standards_version`: Debian Standards-Version.

During development of this templating system you can also replay without
ask and overwritting the configurated files with:

```bash
cookiecutter --replay -f THIS_DIRECTORY
```

`-f` forces to overwrite the generated `/debian` directory and contents.

Sample output:

``` {.bash}
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

$ debuild -us -uc -b
(...)
$ ls -l ../ala-collectory_1.6.2-1_all.deb
-rw-r--r-- 1 vjrj vjrj 65608156 ago 23 12:30 ../ala-collectory_1.6.2-1_all.deb
```

## TODO

- [x] File perms
- [x] tomcat properly context configuration
- [x] db users/db

## Credits

This generator is a fork of the project [cookiecutter-debian-python-module](https://github.com/fladi/cookiecutter-debian-python-module). So thanks indeed.
