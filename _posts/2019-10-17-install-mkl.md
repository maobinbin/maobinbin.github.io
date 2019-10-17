---
layout: post
title: Ubuntu MKL
categories: linux
description: how to install mkl
keywords: linux, mkl
---


https://software.seek.intel.com/performance-libraries

	
$ sudo ./install.sh
'''shell
source /opt/intel/bin/compilervars.sh intel64
export CMAKE_INCLUDE_PATH=/opt/intel/compilers_and_libraries_2018.2.199/linux/mkl/include
export MAKE_LIBRARY_PATH=/opt/intel/compilers_and_libraries_2018.2.199/linux/mkl/lib/intel64:/opt/intel/compilers_and_libraries_2018.2.199/linux/compiler/lib/intel64
export LD_LIBRARY_PATH=$CMAKE_LIBRARY_PATH:$LD_LIBRARY_PATH
'''
source .bashrc
