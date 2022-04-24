BUILD_DIR=../../build
TOOL_DIR=../../build/tools
TOOL_BIN_DIR=${TOOL_DIR}/bin

all: clean
	mkdir -p ${BUILD_DIR}
	mkdir -p ${TOOL_DIR}
	cd ../../tools/build; \
	./bootstrap.sh; \
	./b2 install --prefix=${TOOL_DIR};
	cd ../../; \
	./build/tools/bin/bjam cflags="-m32 -march=i386" \
	cxxflags="-m32 -march=i386" \
	address-model=32 \
	threading=multi \
	architecture=x86 \
	instruction-set=i586 \
	--build-dir=./build --stagedir=./build/stage toolset=gcc stage

clean:
	rm -rf ${BUILD_DIR}
