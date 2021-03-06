baresip-android
===============

Baresip for Android


This project shows how to build baresip for Android NDK.
Baresip is a modular SIP-client with audio/video support
that supports many target platforms. Baresip can be used
as a standalone console application, or as a powerful
toolkit (libbaresip) for 3rd-party applications.


## Supported NDKs

| NDK: | Supported: |
|------|------------|
| r16  | Yes        |
| r15  | Yes        |
| r14  | Yes        |
| r13  | No         |



## Step 1 - download source code

Download baresip/librem/libre source from creytiv.com [1]

```
$ wget http://www.creytiv.com/pub/baresip-0.5.9.tar.gz
$ wget http://www.creytiv.com/pub/rem-0.5.3.tar.gz
$ wget http://www.creytiv.com/pub/re-0.5.8.tar.gz
$ wget http://www.creytiv.com/pub/retest-0.5.2.tar.gz

$ # .. and download OpenSSL source from openssl.org [2]
$ wget https://www.openssl.org/source/openssl-1.1.0h.tar.gz

$ # .. and download Opus source from opus.org [5] (optional)
$ wget http://downloads.xiph.org/releases/opus/opus-1.1.3.tar.gz

$ # .. and download ZRTP source from github.com [7] (optional)
$ wget https://github.com/juha-h/libzrtp/archive/master.zip

$ # .. download Android NDK from [3]
```



## Step 2 - unpack source code

unpack the source code in the current directory, or create
symlinks to the source code so that you have a layout like this:

    baresip/
    openssl/
    opus/ (optional)
    libzrtp/ (optional)
    re/
    rem/



## Step 3 - build openssl

libre depends on openssl for crypto and TLS.

```
$ make openssl
```



## Step 4 - build opus, zrtp (optional)

```
$ make opus
$ make zrtp
```



## Step 5 - build baresip + libs

baresip depends on librem and libre.

```
$ make baresip
```

this will create a statically linked binary in baresip/baresip




## Step 6 - install baresip in Emulator or target

```
$ make install
```

this will use adb to install baresip in your configured Android emulator.
you can also copy the binary to an Android device using ssh.


## Run test program on Android target

```
$ make test
```

this will compile retest and install it on your configured
Android device, and then run the whole test program.



## Support

if you have questions or issues you are welcome to join our
mailing-list [4] and contribute patches here :)




## References:

- [1] www.creytiv.com
- [2] www.openssl.org
- [3] http://developer.android.com/tools/sdk/ndk/index.html
- [4] http://lists.creytiv.com/mailman/listinfo/re-devel
- [5] http://opus-codec.org
- [7] https://github.com/juha-h/libzrtp
