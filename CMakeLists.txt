cmake_minimum_required(VERSION 3.12)
project(memlog)

set(CMAKE_CXX_STANDARD 17)

include_directories(src/lib)

add_library(memlog
        src/lib/log.cpp
        src/lib/log.h
        src/lib/ringbuffer.cpp
        src/lib/ringbuffer.h
        src/lib/atomic.cpp
        src/lib/atomic.h
        src/lib/stream.cpp
        src/lib/stream.h
        src/lib/collector.cpp
        src/lib/stringformat.cpp
        src/lib/stringformat.h)

add_executable(memlogTest
        src/lib/log.cpp
        src/lib/log.h
        src/lib/ringbuffer.cpp
        src/lib/ringbuffer.h
        src/lib/atomic.cpp
        src/lib/atomic.h
        src/lib/stream.cpp
        src/lib/stream.h
        src/lib/collector.cpp
        src/lib/stringformat.cpp
        src/lib/stringformat.h
        src/test/main.cpp)

target_link_libraries(memlogTest pthread)
