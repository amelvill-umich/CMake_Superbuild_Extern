cmake_minimum_required (VERSION 2.6)

project(SUPERBUILD_EXTERN)

message("Hello from the external repository's CMakeLists.txt!")

# Set Properties->General->Configuration Type to Application(.exe)
# Creates the executable with the listed sources
# and adds sources to the Solution Explorer
add_executable (extern_binary extern.c)

# I'm pretty sure this is supposed to be in the extern, though the forum post kinda makes
# it seem like this should be in the config file instead...?
install (TARGETS extern_binary 
        EXPORT extern_binary #NOTE: this statement must come before RUNTIME_DESTINATION!
        RUNTIME DESTINATION "DirectoryForCmakeSuperbuild_Extern"
        )

install(EXPORT extern_binary
        FILE DepTargets.cmake
        NAMESPACE Extern::
        DESTINATION lib/cmake/Extern
)

configure_file("${CMAKE_SOURCE_DIR}/SUPERBUILD_EXTERNConfig.cmake.in" SUPERBUILD_EXTERNConfig.cmake @ONLY)

# I think this is what makes sure the Config file is in SUPERBUILD_EXTERN_DIR
install(FILES "${CMAKE_CURRENT_BINARY_DIR}/SUPERBUILD_EXTERNConfig.cmake"
        DESTINATION lib/cmake/Extern
)