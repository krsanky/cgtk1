TARGET=template_app
#CC=gcc
DEBUG=-g
OPT=-O0
WARN=-Wall
#PTHREAD=-pthread
CCFLAGS=$(DEBUG) $(OPT) $(WARN) $(PTHREAD) -pipe
GTKLIB=`pkg-config --cflags --libs gtk+-3.0`

# linker
#LD=gcc
LDFLAGS=$(PTHREAD) $(GTKLIB) -rdynamic

OBJS=    main.o

all: $(OBJS)
	$(LD) -o $(TARGET) $(OBJS) $(LDFLAGS)
    
main.o: src/main.c
	$(CC) -c $(CCFLAGS) src/main.c $(GTKLIB) -o main.o

try:
	cc `pkgconf -cflags gtk+-3.0` src/main.c -o $(TARGET) `pkgconf -libs gtk+-3.0` -rdynamic -Wall
    
clean:
	rm -f *.o $(TARGET)


