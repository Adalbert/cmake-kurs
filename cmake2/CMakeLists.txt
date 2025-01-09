
cmake_minimum_required(VERSION 3.31)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 	   	17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS	OFF)

set(LIBRARY_NAME Library)
set(EXECUTABLE_NAME Test)

option(COMPILE_EXECUTABLE ON)

add_subdirectory(src)

add_executable(${EXECUTABLE_NAME} main.cpp)
target_link_libraries(${EXECUTABLE_NAME} PUBLIC ${LIBRARY_NAME})
