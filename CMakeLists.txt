cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(pico_vl6180x_project C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
pico_sdk_init()

add_library(pico_vl6180x src/pico_vl6180x.cpp)

target_include_directories(pico_vl6180x PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_include_directories(pico_vl6180x PRIVATE ${CMAKE_CURRENT_LIST_DIR}/src)

target_link_libraries(pico_vl6180x
  pico_stdlib
  hardware_i2c
)
