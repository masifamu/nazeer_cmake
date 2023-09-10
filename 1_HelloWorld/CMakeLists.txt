# create main file and cmakelist files
# make a build dir and cd to it.
# cmake .. for generating the build file/configuring the cmake
# cmake --build .
# ./nazeerExecutable

cmake_minimum_required(VERSION 3.22)

#cmake variables
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
# user variables
set(PROJECT_NAME nazeer)
set(LIB_NAME nazeerLibrary)
set(EXECUTABLE_NAME nazeerExecutable)

project(${PROJECT_NAME} VERSION 1.0.0 LANGUAGES C CXX)

add_library(${LIB_NAME} STATIC src/my_lib.cpp)
#target_include_directories(nazeerLibrary PUBLIC "inc")

option(GENERATE_EXECUTABLE "Whether to compile the executable" OFF)
if(GENERATE_EXECUTABLE)
    message("Compiling Executable")
    add_executable(${EXECUTABLE_NAME} app/main.cpp)
    target_link_libraries(${EXECUTABLE_NAME} PUBLIC ${LIB_NAME})
else()
    message("No executable compiled")
endif()