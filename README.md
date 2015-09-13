Squeezelite
===========================
lightweight headless squeezebox emulator

#<a name="index"/>Index
* [HOWTO - Setup](#setup)
	* [GNU/Linux - Debian] (#setup_linux)
	* [BSD - FreeBSD] (#setup_bsd)
* [HOWTO - Compile](#compile)
	* [GNU/Linux - Debian] (#compile_linux)
	* [BSD - FreeBSD] (#compile_bsd)
* [HOWTO - Install](#install)

<a name="setup"/>
##HOWTO - Setup

<a name="setup_linux"/>
###GNU/Linux - Debian

```bash
# apt-get install autoconf automake libtool
# apt-get install libao-dev libasound2-dev libfaad-dev libflac-dev libmad0-dev libmpg123-dev libvorbis-dev
```

<a name="setup_bsd"/>
###BSD - FreeBSD

```bash
# pkg install autoconf automake libtool gmake
# pkg install faad2 flac libmad mpg123 libvorbis portaudio
```

<a name="compile"/>
##HOWTO - Compile

<a name="compile_linux"/>
###GNU/Linux - Debian

```bash
$ ./autogen.sh
$ ./configure
$ make
```

<a name="compile_bsd"/>
###BSD - FreeBSD
 
```bash
$ ./autogen.sh
$ CFLAGS="-I/usr/local/include" LDFLAGS="-L/usr/local/lib" ./configure
$ make
```

<a name="install"/>
##HOWTO - Install

switch to root and install
```bash
$ su - root
# make install
```
