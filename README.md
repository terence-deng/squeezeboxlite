Squeezelite
===========================
lightweight headless squeezebox emulator

#<a name="index"/>Index
* [HOWTO - Setup](#setup)
	* GNU/Linux - Debian (#setup-linux)
	* BSD - FreeBSD (#setup-bsd)
* [HOWTO - Compile](#compile)
	* GNU/Linux - Debian (#compile-linux)
	* BSD - FreeBSD (#compile-bsd)
* [HOWTO - Install](#install)

<a name="setup"/>
##HOWTO - Setup

<a name="setup-linux"/>
###GNU/Linux - Debian

``Bash
apt-get install autoconf automake libtool
apt-get install libao-dev libasound2-dev libfaad-dev libflac-dev libmad0-dev libmpg123-dev libvorbis-dev

<a name="setup-bsd"/>
###BSD - FreeBSD

``Bash
pkg install autoconf automake libtool gmake
pkg install faad2 flac libmad mpg123 libvorbis portaudio

<a name="compile"/>
##HOWTO - Compile

<a name="compile-linux"/>
###GNU/Linux - Debian

``Bash
./autogen.sh
./configure
make

<a name="compile-bsd"/>
###BSD - FreeBSD
 
``Bash
./autogen.sh
CFLAGS="-I/usr/local/include" LDFLAGS="-L/usr/local/lib" ./configure
make

<a name="install"/>
##HOWTO - Install

switch to root and install
``Bash
su - root
make install
