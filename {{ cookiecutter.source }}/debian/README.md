## Intro

You can generate a non-signed debian package via:

```bash
debuild -us -uc -b
```
in the parent of this directory. This will generate the deb file in the parent directory of this repository.

You can increase changelog version and comments with `dch` utility, like with `dch -i` that increase minor version.

## Looking for inspiration?

You can use [tomcat7-examples package](https://salsa.debian.org/java-team/tomcat7/tree/master/debian) for inspiration of tomcat7 packages. Also `dbconfig-common` package have some samples in `/usr/share/doc/dbconfig-common/examples/` for mysql dep packages and postgresql.

## Testing

You can test the generated package without installit with `piuparts` like:

```bash
sudo piuparts -D ubuntu -d xenial -d bionic ../ala-collectory_1.6.2-1_all.deb
```
in this way you can also test it in different releases.

Read `/usr/share/doc/piuparts/README.*` for more usage samples.

## No interactive install

You can preseed this package with something similar to (if this package uses mysql):

```bash
echo "{{ cookiecutter.package }} {{ cookiecutter.package }}/mysql/admin-pass password $DB_ROOT_PWD" | debconf-set-selections && \
echo "{{ cookiecutter.package }} {{ cookiecutter.package }}/dbconfig-install boolean true" | debconf-set-selections && \
echo "{{ cookiecutter.package }} {{ cookiecutter.package }}/dbconfig-upgrade boolean true" | debconf-set-selections

cat > /etc/dbconfig-common/{{ cookiecutter.package }}.conf <<EOF
dbc_dbname='{{ cookiecutter.package.replace('ala-', '') }}'
dbc_dbuser='{{ cookiecutter.package.replace('ala-', '') }}'
dbc_dbpass='password'
EOF

export DEBCONF_FRONTEND=noninteractive
apt-get install -yq --force-yes {{ cookiecutter.package }}
```

Also you can install `dbconfig-no-thanks` to avoid db questions.
