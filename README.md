nagios-plugins-rabbitmq
-----------------------

This repository contains debian control files for creating an Ubuntu package for Trusty Tahr.

Building
========

To build this package, I suggest using pbuilder-dist:

1. Download the source tarball: `make -f debian/Makefile get_source_tarball`
2. Install pbuilder: `apt-get install ubuntu-dev-tools debhelper`.
3. Create a pbuilder environment for Trusty Tahr: `pbuilder-dist trusty create`.
4. Create the source package and .dsc file: `make -f debian/Makefile source_no_sign`.
5. Create the package using pbuilder-dist:  `make -f debian/Makefile pbuild CHANGES=../nagios-nrpe-check-rabbitmq_1.1.0.dsc`.
