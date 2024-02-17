
cmake_minimum_required(VERSION 3.14)

project(test VERSION 1.0 LANGUAGES CXX C ASM)

# cmake flags
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_EXTENSIONS ON) # Same as gnu++2a (ON) vs c++2a (OFF): https://cmake.org/cmake/help/latest/prop_tgt/CXX_EXTENSIONS.html
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_EXTENSIONS ON)
set(CMAKE_C_STANDARD_REQUIRED ON)

set(CMAKE_CXX_FLAGS "-fPIC -O0 -Wall -g")
# https://stackoverflow.com/questions/49455040/typeinfo-symbols-not-exported-from-dynamic-library
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-rtti")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-elide-constructors")

file(GLOB source *.h *.cc)
add_executable(test ${source})





