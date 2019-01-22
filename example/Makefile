CC = gcc
PROJECT_NAME_C = cjpeg
PROJECT_NAME_D = djpeg
MKDIR_PROJECT = mkdir -p
CFLAGS = -O3 -I../library
LDLAGS = -O3
BIN_DIR = bin
OBJ_DIR = obj
OBJS_C = $(OBJ_DIR)/cdjpeg.o $(OBJ_DIR)/cjpeg.o
OBJS_D = $(OBJ_DIR)/cdjpeg.o $(OBJ_DIR)/djpeg.o

all: $(BIN_DIR)/$(PROJECT_NAME_C) $(BIN_DIR)/$(PROJECT_NAME_D)
-include $(OBJS:.o=.d)
$(BIN_DIR)/$(PROJECT_NAME_C): $(OBJS_C)
		$(MKDIR_PROJECT) $(BIN_DIR)
		$(CC) $(LDLAGS) $^ -o $@ $(LDLAGS) -ljpeg -L../library/bin

$(BIN_DIR)/$(PROJECT_NAME_D): $(OBJS_D)
		$(MKDIR_PROJECT) $(BIN_DIR)
		$(CC) $(LDLAGS) $^ -o $@ $(LDLAGS) -ljpeg -L../library/bin

$(OBJ_DIR)/%.o: %.c
		$(MKDIR_PROJECT) $(OBJ_DIR)
		$(CC) -c $(CFLAGS) $< -o $@
		$(CC) -MM -MP -MT $@ -MF $(OBJ_DIR)/$*.d $(CFLAGS) $<

.PHONY : clean

clean:
		rm -rf $(OBJ_DIR)/*.o $(OBJ_DIR)/*.d $(BIN_DIR)/$(PROJECT_NAME_C) $(BIN_DIR)/$(PROJECT_NAME_D)
