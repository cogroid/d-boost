all: clean
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
	export CFLAGS="-v -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include "; \
	export CXXFLAGS="-v -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include "; \
	export ANDROIDNDKROOT=/home/cogroid/local/android-ndk-r18b; \
	export NDKVER=r18b; \
	export CLANGPATH=/home/cogroid/local/android-ndk-r18b/toolchains/llvm/prebuilt/linux-x86_64/bin; \
	export PATH=/home/cogroid/local/android-ndk-r18b/toolchains/arm-linux-androideabi-4.9/prebuilt/linux-x86_64/arm-linux-androideabi/bin:${PATH}; \
	./build/armv7/tools/bin/bjam \
	cflags="-v -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include " \
	cxxflags="-v -ferror-limit=1024 -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++/include -I/home/cogroid/local/android-ndk-r18b/sources/cxx-stl/llvm-libc++abi/include " \
	link=static \
	target-os=android \
	toolset=clang-armeabiv7a \
	threading=multi \
	architecture=arm \
	address-model=32 \
	--layout=tagged \
	--without-python \
	--build-dir=./build/armv7 --stagedir=./build/armv7/stage stage

clean:
	rm -rf ../../build/armv7
