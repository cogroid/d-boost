BUILD_DIR=../../build/i386
TOOL_DIR=../../build/i386/tools
TOOL_BIN_DIR=${TOOL_DIR}/bin

all: clean
	mkdir -p ${BUILD_DIR}
	mkdir -p ${TOOL_DIR}
	cd ../../tools/build; \
	./bootstrap.sh; \
	./b2 install --prefix=${TOOL_DIR};
	cd ../../; \
	./build/i386/tools/bin/bjam \
	link=shared \
	cflags="-m32 -march=i386" \
	cxxflags="-m32 -march=i386" \
	address-model=32 \
	threading=multi \
	architecture=x86 \
	instruction-set=i586 \
	--without-python \
	--build-dir=./build/i386 --stagedir=./build/i386/stage toolset=gcc stage

clean:
	rm -rf ${BUILD_DIR}
