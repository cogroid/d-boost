[![cogroid.com](https://github.com/cogroid/resources/raw/main/images/banner/cogroid-48.png)](https://cogroid.com)

# Boost C++ Libraries

### Packages on Ubuntu 18.04

* [libboost-system1.65.1](https://packages.ubuntu.com/bionic/libboost-system1.65.1)
* [libboost-filesystem1.65.1](https://packages.ubuntu.com/bionic/libboost-filesystem1.65.1)
* [libboost-thread1.65.1](https://packages.ubuntu.com/bionic/libboost-thread1.65.1)
* [libboost-program-options1.65.1](https://packages.ubuntu.com/bionic/libboost-program-options1.65.1)
* [Source Package: boost1.65.1](https://packages.ubuntu.com/source/bionic/boost1.65.1)

### Prerequisites

###### build-essential

```
sudo apt-get install build-essential
```

###### GLIBC == 2.27

```
ldd --version
```

* Ubuntu 18.04

###### GCC 32 bit

```
sudo apt install gcc-multilib

sudo apt install g++-multilib
```

###### NDK r18b

* [NDK Downloads](https://developer.android.com/ndk/downloads)
* [NDK r18b for Linux](https://dl.google.com/android/repository/android-ndk-r18b-linux-x86_64.zip)

```
Unzip to folder /home/cogroid/local/android-ndk-r18b
```

###### clang

```
sudo apt install clang
```

### Build for x64 machine

```
cd ${BOOST_DIR}/make/x64
make
```

### Build for i586 machine

```
cd ${BOOST_DIR}/make/i386
make
```

### Build for armv7-a machine

```
sudo apt update
cd ${BOOST_DIR}/make/armv7
make
```

---
[Head icons created by Freepik - Flaticon](https://www.flaticon.com/free-icons/head)
