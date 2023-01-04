# Python 3 bindings for pjsip

According to the official website "PJSIP is a free and open source multimedia communication library written in C language implementing standard based protocols such as SIP, SDP, RTP, STUN, TURN, and ICE. It combines signaling protocol (SIP) with rich multimedia framework and NAT traversal functionality into high level API that is portable and suitable for almost any type of systems ranging from desktops, embedded systems, to mobile handsets."

To download, you can access the [project page](https://www.pjsip.org/) and click on [Download](https://www.pjsip.org/download.htm).


## Installation Instructions

If you have downloaded the project from the official website, you should have a file similar to * pjproject-x.x.tar.bz2 *, x.x being the PJSIP version.

Run the following commands:
```bash
$ sudo apt install build-essential python3-dev libasound2-dev
$ tar -xf pjproject-x.x.tar.bz2 && cd pjproject-x.x/
$ export CFLAGS="$CFLAGS -fPIC"
$ ./configure --enable-shared
$ make dep
$ make
$ sudo make install
```

With this you already have PJSIP installed on your machine. To work with pysua in python 3, run the following commands:
```bash
$ sudo apt install python3-dev
$ cd pjproject-x.x/pjsip-apps/src/
$ git clone https://github.com/mgwilliams/python3-pjsip.git
$ cd python3-pjsip
$ python3 setup.py build
$ sudo python3 setup.py install
```

You can test the operation of pjsua directly in python:
```bash
$ python3
Python 3.5.2 (default, Nov 23 2017, 16:37:01)
[GCC 5.4.0 20160609] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import pjsua
>>>
```

## Comments

If when you import the package the compiler complains about the lack of some *.so* file, add the `/usr/local/lib` directory to ldconfig - [Explanation](https://unix.stackexchange.com/a/67784/120790).


## Build instructions on Ubuntu 18.04

Detailed build instructions for PJSUA and PSUA2 can be found [here](https://github.com/TamojitSaha/python3-pjsip/wiki/Instruction-for-compiling-PJSUA-and-PJSUA2-in-Ubuntu-18.04)
