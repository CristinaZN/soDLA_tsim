# soDLA_tsim
 attach soDLA to tvm

## tvm

Apache TVM (incubating) is a compiler stack for deep learning systems. It is designed to close the gap between the productivity-focused deep learning frameworks, and the performance- and efficiency-focused hardware backends. TVM works with deep learning frameworks to provide end to end compilation to different backends.
Learn more about TVM on the project web page.

<https://github.com/apache/incubator-tvm>

[TVM Online Documentation](https://docs.tvm.ai/).

## Directory Structure

In this repository, you will find:

	* hardware/ -- hardware model
		* hardware/chisel -- Chisel implementation of soDLA
		* hardware/verilog -- verilog files
	* python/ -- python instructions
	* src/ -- some files for runtime
	* tests/ -- python test

## Building the TVM

  First, check the cmake in your system. If you do not have cmake, you can obtain the latest version from [official website](https://cmake.org/download/)

### Building TVM on Linux 
  Clone the TVM

    $ git clone --recursive https://github.com/apache/incubator-tvm tvm 
  
  Build the Shared Libaray

    $ sudo apt-get update
    $ sudo apt-get install -y python3 python3-dev python3-setuptools gcc libtinfo-dev zlib1g-dev build-essential cmake libedit-dev libxml2-dev

See the [TVM Online Documentation](https://docs.tvm.ai/) for more information.

  Use cmake to build the library.
    $ cd tvm
    $ mkdir build
    $ cp cmake/config.cmake build
    $ cd build
    $ cmake ..
    $ make -j4

### Building TVM on Windows
  TVM support build via MSVC using cmake. The minimum required VS version is Visual Studio Community 2015 Update 3. In order to generate the VS solution file using cmake, make sure you have a recent version of cmake added to your path.

  Clone the TVM

    $ git clone --recursive https://github.com/apache/incubator-tvm tvm 
    $ cd tvm
    $ mkdir build
    $ cd build
    $ cmake -G "Visual Studio 14 2015 Win64" -DCMAKE_BUILD_TYPE=Release -DCMAKE_CONFIGURATION_TYPES="Release" ..

