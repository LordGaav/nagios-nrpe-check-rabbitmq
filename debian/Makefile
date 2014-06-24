PROJECT=nagios-nrpe-check-rabbitmq
KEY=CD9C0E84
DIST=trusty
UPSTREAM_GITHUB=jamesc
UPSTREAM_NAME=nagios-plugins-rabbitmq
UPSTREAM_VERSION=1.1.0
TARBALL=../nagios-nrpe-check-rabbitmq_$(UPSTREAM_VERSION).orig.tar.gz
SRCROOT=$(UPSTREAM_NAME)-$(UPSTREAM_VERSION)

package:
	dpkg-buildpackage -A -us -uc
 
source:
	dpkg-buildpackage -S -k$(KEY)

source_no_sign:
	dpkg-buildpackage -S -us -d
 
upload_to_ppa:
	dput ppa:lordgaav/$(PROJECT) "$(CHANGES)"

clean:
	rm -rv debian/$(PROJECT) || true
	rm -rv debian/$(PROJECT)* || true

pbuild:
	pbuilder-dist "$(DIST)" "$(CHANGES)"

get_source_tarball:
	wget -O "$(TARBALL)" "https://github.com/$(UPSTREAM_GITHUB)/$(UPSTREAM_NAME)/archive/$(UPSTREAM_VERSION).tar.gz"

unzip_source: clean
	tar xvf "$(TARBALL)"
	mv "$(SRCROOT)" src
