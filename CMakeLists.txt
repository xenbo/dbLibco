cmake_minimum_required(VERSION 3.8)
project(Testlibco)

set(CMAKE_CXX_STANDARD 11)

# Set cflags
set(CMAKE_C_FLAGS ${CMAKE_C_FLAGS} -g -fno-strict-aliasing -O2 -Wall -export-dynamic -Wall -pipe  -D_GNU_SOURCE -D_REENTRANT -fPIC -Wno-deprecated -m64)

# Use c and asm
enable_language(C ASM)

# Add source files
set(SOURCE_FILES
        co_epoll.cpp
        co_hook_sys_call.cpp
        co_routine.cpp
        coctx.cpp
        coctx_swap.S
        example_echosvr.cpp)

add_executable(Testlibco ${SOURCE_FILES})
target_link_libraries(Testlibco pthread rt dl )