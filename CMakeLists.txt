cmake_minimum_required (VERSION 2.6)

project(SUPERBUILD_EXTERN)

message("Hello from the external repository's CMakeLists.txt!")

# Creates the executable with the listed sources and adds sources to the Solution Explorer
# (but you won't see main.c in the root (superbuild) solution)
add_executable (extern_binary extern.c)

install (TARGETS extern_binary 
        RUNTIME DESTINATION "DirectoryForCmakeSuperbuild_Extern"
        )