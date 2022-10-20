#1.) create code and cmale file
#2.) mkdir build
#3.) cd build
#4.) cmake ..
#5.) make
#6.) ./Executable

cmake_minimum_required(VERSION 3.16)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES CXX)

add_executable(Executable main.cpp)
