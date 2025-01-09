
## Variables:
##

DEBUG ?= 1
ifeq ($(DEBUG), 1)     #if DEBUG == 1
COMPILER_FLAGS = -g -O0 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
EXECUTABLE_NAME = mainDebug
else
COMPILER_FLAGS = -O3 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
EXECUTABLE_NAME = mainRelease
endif

CXX = g++
COMPILER_CALL = $(CXX) $(COMPILER_FLAGS)

CPP_SRCS = $(wildcard *.cpp)
CPP_OBJECTS = $(patsubst %.cpp, %.o, $(CPP_SRCS))


## pseudo targets:
##
build: $(EXECUTABLE_NAME)

## Targets:
##
#build: clean mylib.o
#	$(COMPILER_CALL) main.cpp mylib.o -o $(EXECUTABLE_NAME)

$(EXECUTABLE_NAME): $(CPP_OBJECTS)
	$(COMPILER_CALL) $^ -o $@

#mylib.o:
#	$(COMPILER_CALL) mylib.cpp -c

execute:
	./$(EXECUTABLE_NAME)


## Patterns:
##
##  $@: the file name of the target
##  $<: the name of the first dependency
##  $^: the names of all dependencies
##
##  exmpl -> 	$(COMPILER_CALL) main.cpp mylib.o -o $(EXECUTABLE_NAME)

%.o: %.cpp
	$(COMPILER_CALL) -c $< -o $@

clean:
	rm -f *.o
