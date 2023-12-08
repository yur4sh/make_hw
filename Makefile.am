AUTOMAKE_OPTIONS = foreign subdir-objects
bin_PROGRAMS = bin/makehw

makehw_SOURCES = main.c func.c

AM_CFLAGS = -Wall -Werror

bin_makehw_SOURCES = $(makehw_SOURCES)

bin_PROGRAMS_INSTALL = $(DESTDIR)$(bindir)
include_HEADERS = $(DESTDIR)$(includedir)

all: $(bin_PROGRAMS)

makehw: main.o func.o
	$(LINK) $(CFLAGS) $(LDFLAGS) -o $@ $^

main.o: main.c func.h
	$(CC) $(AM_CFLAGS) -c -o $@ $<

func.o: func.c func.h
	$(CC) $(AM_CFLAGS) -c -o $@ $<

install-exec-local: all
	$(INSTALL_PROGRAM) $(bin_PROGRAMS) $(bin_PROGRAMS_INSTALL)

install-data-local: func.h
	$(MKDIR_P) $(DESTDIR)$(include_HEADERS)/makehw
	$(INSTALL_DATA) $^ $(DESTDIR)$(include_HEADERS)/makehw

clean-local:
	$(RM) -rf bin/ *.o

clean-all: clean-local
	$(RM) -r $(DESTDIR)$(bindir) $(DESTDIR)$(includedir)/makehw
	$(RM) -rf autom4te.cache .deps depcomp Makefile.in Makefile aclocal.m4 compile configure config.log config.status install-sh missing stamp-h1
