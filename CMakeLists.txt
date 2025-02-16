cmake_minimum_required(VERSION 3.10)

project(gguf_loader)
set(CMAKE_CXX_STANDARD 17)

include_directories(include)
include_directories(src)

file(GLOB SOURCES "src/*.cpp" "src/*.c")

add_library(gguf_loader SHARED ${SOURCES})

add_executable(gguf_loader_demo main.cpp)

target_link_libraries(gguf_loader_demo gguf_loader)

add_executable(gguf_loader_test ${CMAKE_SOURCE_DIR}/test/test-gguf.cpp)
target_link_libraries(gguf_loader_test gguf_loader)
