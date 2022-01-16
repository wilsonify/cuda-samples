all: clean 
MAJOR_VERSION:=1
MINOR_VERSION:=0
PATCH_VERSION:=0

all: clean test

clean:
	rm -rf build

build/VERSION:
	mkdir -p build && echo ${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION} > build/VERSION
	

build/particle_test: build/VERSION
	cd build && cmake .. && make

test: build/particle_test
	cd build && ctest
