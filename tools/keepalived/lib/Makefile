# Makefile
#
# Keepalived OpenSource project.
#
# Copyright (C) 2001-2011 Alexandre Cassen, <acassen@linux-vs.org>

CC	 = gcc
INCLUDES = -I.
CFLAGS	 = -g -O2 $(INCLUDES) \
	   -Wall -Wunused -Wstrict-prototypes
DEFS	 =  -D_WITHOUT_SNMP_
COMPILE	 = $(CC) $(CFLAGS) $(DEFS)

OBJS = 	memory.o utils.o notify.o timer.o scheduler.o \
	vector.o list.o html.o parser.o signals.o logger.o \
	list_head.o buffer.o command.o vty.o
HEADERS = $(OBJS:.o=.h)

.c.o:
	$(COMPILE) -c $<

all:	$(OBJS)

clean:
	rm -f *.a *.o *~

distclean: clean
	rm -f config.h
	rm -f Makefile

memory.o: memory.c memory.h utils.h
utils.o: utils.c utils.h
notify.o: notify.c notify.h
timer.o: timer.c timer.h
scheduler.o: scheduler.c scheduler.h memory.h utils.h
vector.o: vector.c vector.h memory.h
list.o: list.c list.h memory.h
html.o: html.c html.h memory.h
parser.o: parser.c parser.h memory.h
signals.o: signals.c signals.h
logger.o: logger.c logger.h
list_head.o: list_head.c list_head.h
buffer.o: buffer.c buffer.h memory.h
command.o: command.c command.h vector.h memory.h vty.h timer.h \
	config.h logger.h
vty.o: vty.c vty.h scheduler.h timer.h utils.h command.h logger.h \
	memory.h
