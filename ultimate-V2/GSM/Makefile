INCLUDE_FLAGS = -I. -I../ -I../uart -I../include
CFLAGS	      = $(INCLUDE_FLAGS) -Wall -g

ifeq ($(arch),)
CC			  = arm-linux-gcc
AR			  = arm-linux-ar
endif

AFLAGS		  = -r

TARGET = libgsm.a

SOUCE_FILES = $(wildcard *.c)
OBJS = $(patsubst %.c,%.o,$(SOUCE_FILES))

%.o : %.c %.h
	$(CC) -c $(CFLAGS) $< -o $@

%.o : %.c
	$(CC) -c $(CFLAGS) $< -o $@

$(TARGET): $(OBJS)
	$(AR) $(AFLAGS) $(TARGET) $(OBJS)

.PHONY:clean
clean:
	$(RM) $(TARGET) $(OBJS)
