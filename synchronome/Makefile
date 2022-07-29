INCLUDE_DIRS = 
LIB_DIRS = 
CC=gcc

CDEFS=
CFLAGS= -O0 -g $(INCLUDE_DIRS) $(CDEFS)
LIBS= 

HFILES= 
CFILES= capturelib.c seqv4l2.c

SRCS= ${HFILES} ${CFILES}
OBJS= ${CFILES:.c=.o}

all: seqv4l2

clean:
	-rm -f *.o *.d frames/*.pgm frames/*.ppm
	-rm -f seqv4l2

capture: capturelib.o
	$(CC) $(LDFLAGS) $(CFLAGS) -o $@ $@.o capturelib.o -lrt

seqv4l2: seqv4l2.o capturelib.o
	$(CC) $(LDFLAGS) $(CFLAGS) -o $@ $@.o capturelib.o -lpthread -lrt

.c.o:
	$(CC) $(CFLAGS) -c $<
