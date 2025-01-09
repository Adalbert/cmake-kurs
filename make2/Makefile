
## Variables:
##

DEBUG ?= 1
ENABLE_WARNINGS ?= 1
WARNINGS_AS_ERRORS ?= 0

ifeq ($(ENABLE_WARNINGS), 1)     #if DEBUG == 1
CPP_WARNINGS = -Wall -Wextra -Wpedantic
else
CPP_WARNINGS =
endif

ifeq ($(DEBUG), 1)     #if DEBUG == 1
# COMPILER_FLAGS = -g -O0 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
COMPILER_FLAGS = -g -O0 $(CPP_WARNINGS) --std=c++17
EXECUTABLE_NAME = mainDebug
else
#COMPILER_FLAGS = -O3 -Wall -Wextra -Wpedantic -Wconversion --std=c++17
COMPILER_FLAGS = -O3 $(CPP_WARNINGS) --std=c++17
EXECUTABLE_NAME = mainRelease
endif

CPP_COMPILER = g++
COMPILER_CALL = $(CPP_COMPILER) $(COMPILER_FLAGS)

SRC_DIR = src
BUILD_DIR = build

CPP_SRCS = $(wildcard $(SRC_DIR)/*.cpp)
CPP_OBJECTS = $(patsubst $(SRC_DIR)/%.cpp, $(BUILD_DIR)/%.o, $(CPP_SRCS))


all: create build

create:
	mkdir -p $(BUILD_DIR)

## pseudo targets:
##
build: $(CPP_OBJECTS)
	$(COMPILER_CALL) $(CPP_OBJECTS) -o $(BUILD_DIR)/$(EXECUTABLE_NAME)
## Targets:
##
#build: clean mylib.o
#	$(COMPILER_CALL) main.cpp mylib.o -o $(EXECUTABLE_NAME)

#mylib.o:
#	$(COMPILER_CALL) mylib.cpp -c

execute:
	./$(BUILD_DIR)/$(EXECUTABLE_NAME)


## Patterns:
##
$(BUILD_DIR)/%.o: $(SRC_DIR)/%.cpp
	$(COMPILER_CALL) -c $< -o $@


clean:
	rm -f $(BUILD_DIR)/*.o
	rm -f $(BUILD_DIR)/*.exe
