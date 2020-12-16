#
#	makefile
#


# CROSS_COMPILE_ROOT=
# CROSS_COMPILE=$(CROSS_COMPILE_ROOT)/arm-linux-gnueabihf

# CFLAGS = -Wall -std=c++0x -I$(CROSS_COMPILE_ROOT)/arm-linux-gnueabihf/libc/usr/include
CFLAGS = -Wall -std=c++0x

# LIBROOT = $(CROSS_COMPILE_ROOT)/arm-linux-gnueabihf

CC = gcc

LIB = -static -static-libgcc -static-libstdc++ -Wl,-Bstatic -lpthread -lm

DEST =  mytest.out

all:	$(DEST) Makefile

%.o: %.cpp
	$(CC) -c $(CFLAGS) $< -o $@ $(INCLUDE) 
clean:
	rm -rf *.o *.out
mytest.out: main.o
          
	$(CC) $(LIB) $(CFLAGS) \
	$(ACELIB) $(SQLLIB) \
		main.o

release:
	
