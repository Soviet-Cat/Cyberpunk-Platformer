cmake_minimum_required(VERSION 3.10)
project(CyberpunkPlatformer VERSION 0.0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 26)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SRC "${CMAKE_CURRENT_BINARY_DIR}/../src/")
set(BIN "${CMAKE_CURRENT_BINARY_DIR}/../bin/")

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -mwindows")

add_definitions(-DUNICODE)

set(CyberpunkPlatformer_SOURCES
    ${SRC}main.cpp
)

include_directories(${SRC})

add_executable(CyberpunkPlatformer ${CyberpunkPlatformer_SOURCES})
set_target_properties(CyberpunkPlatformer PROPERTIES OUTPUT_NAME "CyberpunkPlatformer-Windows-x86_64")
set_target_properties(CyberpunkPlatformer PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${BIN})
set_target_properties(CyberpunkPlatformer PROPERTIES LINK_FLAGS "-static")
target_link_libraries(CyberpunkPlatformer PRIVATE stdc++ gcc d2d1 dwrite windowscodecs urlmon)