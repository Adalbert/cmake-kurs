
cmake_minimum_required(VERSION 3.31)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES CXX)

# variablennamen setzen:
set(EXECUTABLE_NAME Executable)
set(LIBRARY_NAME Library)

# library erstellen
add_library(${LIBRARY_NAME} mylib.cpp)

add_executable(${EXECUTABLE_NAME} main.cpp)

# target linken
target_link_libraries(${EXECUTABLE_NAME} ${LIBRARY_NAME})
