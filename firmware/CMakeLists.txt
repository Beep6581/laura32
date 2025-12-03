cmake_minimum_required(VERSION 3.16)

project(laura32_firmware C CXX)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Allow switching easily between C and C++ entry points later.
set(SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src)

file(GLOB FIRMWARE_SOURCES
    ${SRC_DIR}/*.c
    ${SRC_DIR}/*.cpp
)

add_executable(laura32_firmware ${FIRMWARE_SOURCES})

# Add any include directories here, for example:
# target_include_directories(laura32_firmware PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
