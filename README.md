# CMake_Superbuild_Extern

This repository is a part of an example of how to work with ExternalProject_Add and CPack. 
It just builds a "hello world" application; in a more practical situation it would probably make a shared library.

This root repository will:
- Build extern.c into extern_binary, and install it into a relative folder so that it can be packaged by the [root / superbuild repository](https://github.com/amelvill-umich/CMake_Superbuild_Root).

Thanks to [Florian](https://discourse.cmake.org/u/florian_chevassu/summary) on the [CMake Discourse](https://discourse.cmake.org/t/how-to-install-an-external-project/888) for the advice on making this
