cmake_minimum_required(VERSION 3.10)

project(gguf_loader)
set(CMAKE_CXX_STANDARD 17)

include_directories(include)
file(GLOB SOURCES "src/*.cpp")

add_library(gguf_loader SHARED ${SOURCES})

add_executable(gguf_loader_test main.cpp)

target_link_libraries(gguf_loader_test gguf_loader)
