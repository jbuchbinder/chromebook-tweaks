VERSION := `date +%Y%m%d%H%M%S`
GOROOT  ?= /opt/go
SERIAL  := 0

all: rpm

rpm:
	fpm -s dir \
		--verbose \
		-t deb \
		-n galliumos-ubuntu-repo \
		-v ${VERSION} \
		--iteration "${SERIAL}" \
		--url http://www.ravemobilesafety.com/ \
		--vendor "Jeffreu Buchbinder" \
		--maintainer "Jeff Buchbinder <j.buchbinder@dayvillefire.gov>" \
		--description "GalliumOS tweaks" \
		--rpm-os linux \
		--rpm-tag '%define _build_id_links none' \
		--rpm-tag '%undefine _missing_build_ids_terminate_build' \
		./ubuntu.list=/etc/apt/sources.list.d/ \
		./ubuntu-new.pref=/etc/apt/preferences.d/

