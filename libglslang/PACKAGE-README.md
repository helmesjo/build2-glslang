# libglslang - GLSL and ESSL compiler front-end and SPIR-V generator C++ library

This is a `build2` package for the [`glslang`](https://github.com/KhronosGroup/glslang)
C++ library. It is the Khronos reference front-end for GLSL and ESSL, with a
SPIR-V generator. Public headers are included as `<glslang/...>`, matching
upstream's installed layout.


## Usage

To start using `libglslang` in your project, add the following `depends`
value to your `manifest`, adjusting the version constraint as appropriate:

```
depends: libglslang ^16.5.0
```

Then import the library target(s) you need in your `buildfile`:

```
import libs = libglslang%lib{glslang}
import libs += libglslang%lib{glslang-default-resource-limits}
```


## Importable targets

This package provides the following importable targets:

```
lib{glslang}
lib{glslang-default-resource-limits}
lib{SPIRV}
```

`lib{glslang}` is the compiler library (GLSL/ESSL/HLSL front-end, SPIR-V
back-end, C and C++ APIs). `lib{glslang-default-resource-limits}` provides
`GetDefaultResources()` and the C wrappers in
`<glslang/Public/resource_limits_c.h>`. `lib{SPIRV}` is upstream's stub SPIRV
library. It re-exports `lib{glslang}` (the SPIR-V sources are compiled into
`lib{glslang}`).

Public headers install under `include/glslang/`. Typical includes:

```
#include <glslang/Public/ShaderLang.h>
#include <glslang/Public/ResourceLimits.h>
#include <glslang/SPIRV/GlslangToSpv.h>
#include <glslang/Include/Types.h>
#include <glslang/build_info.h>
```


## Configuration variables

This package has no configuration variables.

HLSL support is compiled in, matching upstream's current default. The HLSL
front-end is deprecated upstream. SPIRV-Tools optimization (`ENABLE_OPT`) is
off because there is no build2 SPIRV-Tools package. The library is compiled
with RTTI and exceptions disabled, matching upstream.
