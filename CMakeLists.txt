cmake_minimum_required(VERSION 3.16...3.30)

project(
  MultiplyTest
  LANGUAGES CXX
)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)  # Required by clangd language server.

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

enable_testing()

add_subdirectory(src)
add_subdirectory(tests)
