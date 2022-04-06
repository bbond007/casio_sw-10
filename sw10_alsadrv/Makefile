CC_ARM=arm-linux-gnueabihf-
CC_X86=
BIN_ARM=sw10_alsadrv
BIN_X86=sw10_alsadrv_x86
CCFLAGS_ARM=-Ialsa/include -Lalsa/lib -Ofast -mcpu=cortex-a9 -mtune=cortex-a9 -mfpu=neon -mfloat-abi=hard -ftree-vectorize -funsafe-math-optimizations
LDFLAGS=-lasound -lm -pthread -Wall 

all: sw10_alsadrv x86

sw10_alsadrv: sw10_alsadrv.c ../VLSG/VLSG.c ../VLSG/VLSG.h
	$(CC_ARM)gcc $(CCFLAGS_ARM) $(LDFLAGS) -o $(BIN_ARM) sw10_alsadrv.c ../VLSG/VLSG.c -I../VLSG
	$(CC_ARM)strip $(BIN)
	
x86: sw10_alsadrv.c ../VLSG/VLSG.c ../VLSG/VLSG.h
	$(CC_X86)gcc $(LDFLAGS) -o $(BIN_X86) sw10_alsadrv.c ../VLSG/VLSG.c -I../VLSG 
	$(CC_X86)strip $(BIN_X86)
	
.PHONY: clean
clean:
	rm -f $(BIN_ARM) $(BIN_X86) 
