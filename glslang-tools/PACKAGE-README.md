# glslang-tools - GLSL and ESSL compiler front-end command line tool

This is a `build2` package for the [`glslang`](https://github.com/KhronosGroup/glslang)
command line tool. It is the standalone wrapper around the Khronos GLSL and
ESSL reference front-end (historically named `glslangValidator`).


## Usage

To start using `glslang-tools` in your project, add the following build-time
`depends` value to your `manifest`, adjusting the version constraint as
appropriate:

```
depends: * glslang-tools ^16.5.0
```

Then import the executable in your `buildfile`:

```
import glslang = glslang-tools%exe{glslang}
```


## Importable targets

This package provides the following importable targets:

```
exe{glslang}
```

This is upstream's `glslang-standalone` target, with output name `glslang`.
Debian ships it as `glslang-tools`. The compatibility name `glslangValidator`
is also installed next to `glslang`.


## Configuration variables

This package has no configuration variables.
