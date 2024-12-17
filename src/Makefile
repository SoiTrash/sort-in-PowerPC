AS = powerpc-linux-gnu-as
LD = powerpc-linux-gnu-ld
QEMU = qemu-ppc-static

SRC = SortPowerPC
OBJ = SortPowerPC.o
BIN = ../tests/SortPowerPC

TEST_INPUT = ../tests/test_input.bin
EXPECTED_OUTPUT = ../tests/expected_output.bin
RESULTS_LOG = ../tests/results.log

all: build

build:
	$(AS) -o $(OBJ) $(SRC)
	$(LD) -o $(BIN) $(OBJ)

run: build
	$(QEMU) $(BIN) < $(TEST_INPUT) > output.bin
	diff output.bin $(EXPECTED_OUTPUT) > /dev/null
	@echo "Test Passed!" > $(RESULTS_LOG) || echo "Test Failed!" > $(RESULTS_LOG)

clean:
	rm -f $(OBJ) $(BIN) output.bin $(RESULTS_LOG)
