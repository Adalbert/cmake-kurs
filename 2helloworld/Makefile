
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

SRC_DIR = src
BUILD_DIR = build

CPP_SRCS = $(wildcard $(SRC_DIR)/*.cpp)
CPP_OBJECTS = $(patsubst $(SRC_DIR)/%.cpp, $(BUILD_DIR)/%.o, $(CPP_SRCS))


## pseudo targets:
##
build: $(BUILD_DIR)/$(EXECUTABLE_NAME)

## Targets:
##
#build: clean mylib.o
#	$(CPP_COMPILER_CALL) main.cpp mylib.o -o $(EXECUTABLE_NAME)

$(BUILD_DIR)/$(EXECUTABLE_NAME): $(CPP_OBJECTS)
	$(CPP_COMPILER_CALL) $^ -o $@

#mylib.o:
#	$(CPP_COMPILER_CALL) mylib.cpp -c

execute:
	./$(BUILD_DIR)/$(EXECUTABLE_NAME)


## Patterns:
##
$(BUILD_DIR)/%.o: $(SRC_DIR)/%.cpp
	$(CPP_COMPILER_CALL) -c $< -o $@

clean:
	rm -f $(BUILD_DIR)/*.o
