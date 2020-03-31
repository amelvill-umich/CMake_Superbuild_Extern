cmake_minimum_required (VERSION 2.6)

message("Hello from the external repository's CMakeLists.txt!")

# Set Properties->General->Configuration Type to Application(.exe)
# Creates the executable with the listed sources
# and adds sources to the Solution Explorer
add_executable (extern_binary extern.c)

# Adds logic to INSTALL.vcproj to copy the compiled application to destination directory
install (TARGETS extern_binary
         RUNTIME DESTINATION "DirectoryForCmakeSuperbuild_Extern")