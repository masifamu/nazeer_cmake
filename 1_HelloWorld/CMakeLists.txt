# create main file and cmakelist files
# make a build dir and cd to it.
# cmake .. for generating the build file/configuring the cmake
# cmake --build .
# .nazeerExecutable

cmake_minimum_required(VERSION 3.22)
project(nazeer VERSION 1.0.0 LANGUAGES C CXX)

add_library(nazeerLibrary STATIC src/my_lib.cpp)
#target_include_directories(nazeerLibrary PUBLIC "inc")

add_executable(nazeerExecutable app/main.cpp)

target_link_libraries(nazeerExecutable PUBLIC nazeerLibrary)
