project(siminusminus)
cmake_minimum_required(VERSION 2.8)

# Install dependencies first:
execute_process(
    COMMAND conan install "${CMAKE_SOURCE_DIR}" --build=outdated
    WORKING_DIRECTORY "${CMAKE_BINARY_DIR}"
)

# Import dependencies:
include("${CMAKE_BINARY_DIR}/conanbuildinfo.cmake")
conan_define_targets()

add_subdirectory(src)
enable_testing()
add_subdirectory(test)
