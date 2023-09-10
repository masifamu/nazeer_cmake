# create main file and cmakelist files
# make a build dir and cd to it.
# cmake .. for generating the build file/configuring the cmake
# cmake --build
# .nazeerExecutable

cmake_minimum_required(VERSION 3.22)
project(
    nazeer 
    VERSION 1.0.0 
    LANGUAGES C CXX)
add_executable(nazeerExecutable main.cpp)