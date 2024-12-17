CC = as
LD = ld
EMU = qemu-ppc64
SRC = SortPowerPC.s
OBJ = SortPowerPC.o
BIN_DIR = ../bin
BIN = $(BIN_DIR)/SortPowerPC

all: build

build:
	@mkdir -p $(BIN_DIR)           # Ensure bin directory exists
	$(CC) -o $(OBJ) $(SRC)         # Assemble source code
	$(LD) -o $(BIN) $(OBJ)         # Link to create executable

run:
	$(EMU) $(BIN)

clean:
	rm -f $(OBJ) $(BIN)
