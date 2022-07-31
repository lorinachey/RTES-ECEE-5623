INCLUDE_DIRS = 
LIB_DIRS = 
CC=gcc

CDEFS=
CFLAGS= -O0 -g $(INCLUDE_DIRS) $(CDEFS)
LIBS= 

HFILES= 
CFILES= image_capture_and_processing.c main_sequencer.c

SRCS= ${HFILES} ${CFILES}
OBJS= ${CFILES:.c=.o}

all: main_sequencer

clean:
	-rm -f *.o *.d frames/*.pgm frames/*.ppm
	-rm -f main_sequencer

capture: image_capture_and_processing.o
	$(CC) $(LDFLAGS) $(CFLAGS) -o $@ $@.o image_capture_and_processing.o -lrt

main_sequencer: main_sequencer.o image_capture_and_processing.o
	$(CC) $(LDFLAGS) $(CFLAGS) -o $@ $@.o image_capture_and_processing.o -lpthread -lrt

.c.o:
	$(CC) $(CFLAGS) -c $<
