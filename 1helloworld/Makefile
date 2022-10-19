
## Variables:
##

DEBUG ?= 1
ifeq ($(DEBUG), 1)     #if DEBUG == 1
CPP_COMPILER_FLAGS = -g -O0 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
EXECUTABLE_NAME = mainDebug
else
CPP_COMPILER_FLAGS = -O3 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
EXECUTABLE_NAME = mainRelease
endif

CPP_COMPILER = g++
CPP_COMPILER_CALL = $(CPP_COMPILER) $(CPP_COMPILER_FLAGS)

CPP_SRCS = $(wildcard *.cpp)
CPP_OBJECTS = $(patsubst %.cpp, %.o, $(CPP_SRCS))


## pseudo targets:
##
build: $(EXECUTABLE_NAME)

## Targets:
##
#build: clean mylib.o
#	$(CPP_COMPILER_CALL) main.cpp mylib.o -o $(EXECUTABLE_NAME)

$(EXECUTABLE_NAME): $(CPP_OBJECTS)
	$(CPP_COMPILER_CALL) $^ -o $@

#mylib.o:
#	$(CPP_COMPILER_CALL) mylib.cpp -c

execute:
	./$(EXECUTABLE_NAME)


## Patterns:
##
%.o: %.cpp
	$(CPP_COMPILER_CALL) -c $< -o $@

clean:
	rm -f *.o
