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
FROM ubuntu:20.04

ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get -y update --fix-missing && apt-get -y install apt-utils gnupg
RUN apt-get -y update --fix-missing && apt-get -y upgrade
RUN apt-get install -y libselinux1 apt-file
RUN apt-get install -y kmod make gcc wget unar
RUN apt-get install -y rpm2cpio cpio fuse file

RUN apt-get install -y python3
RUN ln -s /usr/bin/python3 /usr/bin/python

RUN apt-get install -y libzita-resampler-dev
RUN apt-get install -y libzita-convolver-dev
RUN apt-get install -y ladspa-sdk
RUN apt-get install -y libgtk2.0-dev
RUN apt-get install -y libgtkmm-2.4-dev
RUN apt-get install -y libsigc++-2.0-dev libsigc++-2.0-0v5
RUN apt-get install -y libsndfile1-dev
RUN apt-get install -y libjack-dev
RUN apt-get install -y libjack-jackd2-dev
RUN apt-get install -y libboost-dev
RUN apt-get install -y libwebkit2gtk-4.0-dev
RUN apt-get install -y libglib2.0-dev
RUN apt-get install -y intltool
RUN apt-get install -y libcurl4-gnutls-dev
RUN apt-get install -y sassc
RUN apt-get install -y libgtkmm-3.0-dev
RUN apt-get install -y liblrdf0-dev
RUN apt-get install -y liblilv-dev
RUN apt-get install -y libboost-system-dev
RUN apt-get install -y libboost-iostreams-dev
RUN apt-get install -y gperf
RUN apt-get install -y faust
RUN apt-get install -y libavahi-gobject-dev
RUN apt-get install -y bluez
RUN apt-get install -y liblo-dev
RUN apt-get install -y libeigen3-dev
RUN apt-get install -y fonts-roboto
RUN apt-get install -y libbluetooth-dev
RUN apt-get install -y libavcodec-dev
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
# RUN apt-get install -y 
