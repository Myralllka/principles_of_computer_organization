C = gcc
# add -O3 to compile with optimization and -d to compile with debuging to the CFLAGS variable
CFLAGS = -c 
TARGETS = bzip2 bzip2recover
NAME_O = bzip2
NAME_T = bzip2recover
BIN_D = bin
OBJ_D = obj
SO = ../library/bin/libbzip2.so

all: mdr $(BIN_D)/$(NAME_O) $(BIN_D)/$(NAME_T)

mdr:
	test -d bin || mkdir $(BIN_D)
	test -d obj || mkdir $(OBJ_D)

$(BIN_D)/$(NAME_O): $(OBJ_D)/$(NAME_O).o
	$(C) $(OBJ_D)/$(NAME_O).o -o $(NAME_O) $(SO)

$(BIN_D)/$(NAME_T): $(OBJ_D)/$(NAME_T).o
	$(C) $(OBJ_D)/$(NAME_T).o -o $(NAME_T) $(SO)

$(OBJ_D)/%.o: %.c
	$(C) $(CFLAGS) $< -o $@

.PHONY : clean
clean: 
	rm -rf obj/ bin/
