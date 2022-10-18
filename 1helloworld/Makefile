
## Variables:
##

DEBUG ?= 0
ifeq ($(DEBUG), 1)     #if DEBUG == 1
CPP_COMPILER_FLAGS = -g -O0 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
EXECUTABLE_NAME = mainDebug
else
CPP_COMPILER_FLAGS = -O3 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
EXECUTABLE_NAME = mainRelease
endif

CPP_COMPILER = g++
CPP_COMPILER_CALL = $(CPP_COMPILER) $(CPP_COMPILER_FLAGS)


## Targets:
##
build: mylib.o
	$(CPP_COMPILER_CALL) main.cpp mylib.o -o $(EXECUTABLE_NAME)

mylib.o:
	$(CPP_COMPILER_CALL) mylib.cpp -c

execute:
	./$(EXECUTABLE_NAME)
