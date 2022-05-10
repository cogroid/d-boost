all: clean
	sudo ln -s /home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a/libc++_shared.so /home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a/libc++.so
	mkdir -p ../../build/armv7
	mkdir -p ../../build/armv7/tools
	cd ../../tools/build; \
	cp -f ../../make/armv7/user-config.jam ./example/; \
	cp -f ../../make/armv7/user-config.jam ./src/; \
	cp -f ../../make/armv7/operations.cpp ../../libs/filesystem/src/; \
	./bootstrap.sh; \
	cp -f ../../make/armv7/user-config.jam ./example/; \
	cp -f ../../make/armv7/user-config.jam ./src/; \
	./b2 install --prefix=../../build/armv7/tools;
	cd ../../; \
	export CFLAGS="-v -stdlib=libc++ -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include -L/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a -B/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a "; \
	export CXXFLAGS="-v -stdlib=libc++ -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include -L/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a -B/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a "; \
	export ANDROIDNDKROOT=/home/cogroid/local/android-ndk-r18b; \
	export NDKVER=r18b; \
	export CLANGPATH=/home/cogroid/local/android-ndk-r18b/toolchains/llvm/prebuilt/linux-x86_64/bin; \
	export PATH=/home/cogroid/local/android-ndk-r18b/toolchains/arm-linux-androideabi-4.9/prebuilt/linux-x86_64/arm-linux-androideabi/bin:${PATH}; \
	./build/armv7/tools/bin/bjam \
	-q \
	cflags="-v -stdlib=libc++ -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include -L/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a -B/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a " \
	cxxflags="-v -stdlib=libc++ -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include -L/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a -B/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a " \
	linkflags="-v -stdlib=libc++ -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include -L/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a -B/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/libs/armeabi-v7a " \
	link=shared \
	binary-format=elf \
	abi=aapcs \
	target-os=android \
	toolset=clang-armeabiv7a \
	threading=multi \
	architecture=arm \
	address-model=32 \
	--layout=system \
	--without-python \
	--build-dir=./build/armv7 --includedir=./build/armv7/install/include --libdir=./build/armv7/install/libs/armeabi-v7a install

clean:
	rm -rf ../../build/armv7
