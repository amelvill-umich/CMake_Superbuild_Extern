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