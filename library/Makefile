CC = gcc
CFAGS = -O3 -fPIC
LDLAGS = -O3
PROJECT_NAME = libjpeg
MKDIR_PROJECT = mkdir -p
BIN_DIR = bin
OBJ_DIR = obj
SOURCES = $(wildcard *.c)
OBJS = $(patsubst %.c,$(OBJ_DIR)/%.o,$(SOURCES))

all: $(BIN_DIR)/$(PROJECT_NAME).a $(BIN_DIR)/$(PROJECT_NAME).so
-include $(OBJS:.o=.d)
$(BIN_DIR)/$(PROJECT_NAME).a: $(OBJS)
	$(MKDIR_PROJECT) $(BIN_DIR)
	ar rcs $@ $^ -o

$(BIN_DIR)/$(PROJECT_NAME).so: $(OBJS)
	$(CC) -dynamiclib -o $(BIN_DIR)/$(PROJECT_NAME).dylib -dy $^

$(OBJ_DIR)/%.o: %.c
	$(MKDIR_PROJECT) $(OBJ_DIR)
	$(CC) -c $(CFLAGS) $< -o $@
	$(CC) -MM -MP -MT $@ -MF $(OBJ_DIR)/$*.d $(CFLAGS) $<

.PHONY : clean
clean:
	rm -rf $(OBJ_DIR)/*.o $(OBJ_DIR)/*.d $(BIN_DIR)/$(PROJECT_NAME)}
