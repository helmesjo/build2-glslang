# glslang - GLSL and ESSL compiler front-end and SPIR-V generator

This is a `build2` package repository for
[`glslang`](https://github.com/KhronosGroup/glslang), the Khronos reference
front-end for GLSL and ESSL, with a SPIR-V generator. It contains:

- `libglslang` - the compiler library
- `glslang-tools` - the `glslang` command line tool

This file contains setup instructions and other details that are more
appropriate for development rather than consumption. If you want to use
`glslang` in your `build2`-based project, then instead see the accompanying
[`libglslang/PACKAGE-README.md`](libglslang/PACKAGE-README.md) and
[`glslang-tools/PACKAGE-README.md`](glslang-tools/PACKAGE-README.md) files.

The development setup for `glslang` uses the standard `bdep`-based workflow.
For example:

```
git clone --recursive https://github.com/build2-packaging/glslang.git
cd glslang

bdep init -C @gcc cc config.cxx=g++
bdep update
bdep test
```
