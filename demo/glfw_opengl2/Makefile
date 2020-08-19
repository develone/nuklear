# Install
BIN = demo

# Flags
CFLAGS += -std=c99 -pedantic -O2 
#CFLAGS += -std=c99 -pedantic -O2 -DINCLUDE_NODE_EDITOR
#CFLAGS += -std=c99 -pedantic -O2 -DINCLUDE_OVERVIEW

SRC = main.c
OBJ = $(SRC:.c=.o)

ifeq ($(OS),Windows_NT)
BIN := $(BIN).exe
LIBS = -lglfw3 -lopengl32 -lm -lGLU32
else
	UNAME_S := $(shell uname -s)
	ifeq ($(UNAME_S),Darwin)
		LIBS := -lglfw3 -framework OpenGL -framework Cocoa -framework IOKit -framework CoreVideo -lm -lGLEW -L/usr/local/lib
	else
		LIBS = -lglfw3 -lGL -lm -lGLU -lX11 -lGL -lm -lGLU -lGLEW -ldl -lpthread
	endif
endif

$(BIN):
	@mkdir -p bin
	rm -f bin/$(BIN) $(OBJS)
	$(CC) $(SRC) $(CFLAGS) -o bin/$(BIN) $(LIBS)
