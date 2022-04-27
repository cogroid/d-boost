BUILD_DIR=../../build/x64
TOOL_DIR=../../build/x64/tools
TOOL_BIN_DIR=${TOOL_DIR}/bin

all: clean
	mkdir -p ${BUILD_DIR}
	mkdir -p ${TOOL_DIR}
	cd ../../tools/build; \
	./bootstrap.sh; \
	./b2 install --prefix=${TOOL_DIR};
	cd ../../; \
	./build/x64/tools/bin/bjam --build-dir=./build/x64 --stagedir=./build/x64/stage toolset=gcc --without-python link=shared stage

clean:
	rm -rf ${BUILD_DIR}
