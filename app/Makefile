# Copyright 2020 Alex Woroschilow (alex.woroschilow@gmail.com)
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
PWD:=$(shell pwd)


.PHONY: all

all: clean init
	mkdir --parents $(PWD)/build/tmp
	mkdir --parents $(PWD)/build/Boilerplate.AppDir

	wget https://master.dl.sourceforge.net/project/guitarix/guitarix/guitarix2-0.39.0.tar.xz?viasf=1 \
		--output-document=$(PWD)/build/guitarix2-0.39.0.tar.xz

	unar $(PWD)/build/guitarix*.tar.xz  \
		-output-directory=$(PWD)/build

	cd $(PWD)/build/guitarix*/ && ./waf configure --prefix=$(PWD)/build/tmp
	cd $(PWD)/build/guitarix*/ && sed -i -e 's#$(PWD)/build/tmp#./..#g' ./build/config.h

	cd $(PWD)/build/guitarix*/ && ./waf build
	cd $(PWD)/build/guitarix*/ && ./waf install --force

	cp --recursive --force $(PWD)/build/tmp/* \
		$(PWD)/build/Boilerplate.AppDir

	$(PWD)/bin/Apprepo.AppImage --destination=$(PWD)/build appdir boilerplate \
	    libgdk-pixbuf2.0-0 libatk1.0-0 libatk-bridge2.0-0 libgtk2.0-0 adwaita-icon-theme \
	    libreadline8 at-spi2-core libpango-1.0-0 libselinux1 libgtk-3-0 libwayland-cursor0 \
		libgxwmm0 liblo7 fonts-roboto liblrdf0 libjack-jackd2-0 libgxw0 liblo7  gxw-glade \
		libpangomm-1.4-1v5 libglibmm-2.4-1v5 libatkmm-1.6-1v5  libgtkmm-3.0-1v5 \
		libglibmm-2.4-1v5 libcairomm-1.0-1v5 libsigc++-2.0-0v5 libavahi-gobject0 \
		libboost-iostreams1.71.0 libzita-convolver3 libzita-resampler1 \
		gnome-themes-extra gnome-themes-standard

	echo ''                      >> $(PWD)/build/Boilerplate.AppDir/AppRun
	echo 'cd $${APPDIR}/bin'     >> $(PWD)/build/Boilerplate.AppDir/AppRun
	echo './guitarix "$${@}"'    >> $(PWD)/build/Boilerplate.AppDir/AppRun

	rm --force $(PWD)/build/Boilerplate.AppDir/*.desktop
	cp --force $(PWD)/AppDir/*.desktop $(PWD)/build/Boilerplate.AppDir/
	cp --force $(PWD)/AppDir/*.png $(PWD)/build/Boilerplate.AppDir/     || true

	export ARCH=x86_64 && $(PWD)/bin/appimagetool.AppImage $(PWD)/build/Boilerplate.AppDir $(PWD)/Guitarix.AppImage
	chmod +x $(PWD)/Guitarix.AppImage

init:
	mkdir --parents $(PWD)/bin

	wget https://github.com/area-of-dev/apprepo.AppImage/releases/download/latest/apprepo.AppImage \
		--output-document=$(PWD)/bin/Apprepo.AppImage
	chmod +x $(PWD)/bin/Apprepo.AppImage

	wget https://github.com/AppImage/AppImageKit/releases/download/13/appimagetool-x86_64.AppImage \
		--output-document=$(PWD)/bin/appimagetool.AppImage
	chmod +x $(PWD)/bin/appimagetool.AppImage

clean:
	rm -rf $(PWD)/*.AppImage
	rm -rf $(PWD)/bin/*
	rm -rf $(PWD)/build
