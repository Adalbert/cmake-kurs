
cmake_minimum_required(VERSION 3.16)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES CXX)

# variablennamen setzen:
set(EXECUTABLE_NAME Executable)
set(LIBRARY_NAME Library)

# library erstellen
add_library(${LIBRARY_NAME} src/mylib.cpp)
target_include_directories(${LIBRARY_NAME} PUBLIC src/)

add_executable(${EXECUTABLE_NAME} app/main.cpp)

# target linken
target_link_libraries(${EXECUTABLE_NAME} PUBLIC ${LIBRARY_NAME})
