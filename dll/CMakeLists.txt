cmake_minimum_required(VERSION 2.8.12)
project(ReflectiveDLL)

set(CMAKE_SYSTEM_NAME Windows)
set(CMAKE_SYSTEM_PROCESSOR x86_64)
set(CMAKE_C_COMPILER x86_64-w64-mingw32-gcc)
set(CMAKE_CXX_COMPILER x86_64-w64-mingw32-c++)
set(CMAKE_RC_COMPILER x86_64-w64-mingw32-windres)
set(CMAKE_C_LINK_EXECUTABLE x86_64-w64-mingw32-ld)
set(CMAKE_AR x86_64-w64-mingw32-ar)
set(CMAKE_FIND_ROOT_PATH /usr/x86_64-w64-mingw32/)
set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)

add_definitions(-DREFLECTIVEDLLINJECTION_VIA_LOADREMOTELIBRARYR -DREFLECTIVEDLLINJECTION_CUSTOM_DLLMAIN)
file(GLOB SOURCE_FILES src/*.c src/*.h)
add_library(ReflectiveDLL SHARED ${SOURCE_FILES})
target_include_directories(ReflectiveDLL PUBLIC .)
