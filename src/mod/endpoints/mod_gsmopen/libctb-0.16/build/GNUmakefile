# =========================================================================
#     This makefile was generated by
#     Bakefile 0.2.5 (http://www.bakefile.org)
#     Do not modify, all changes will be overwritten!
# =========================================================================



# -------------------------------------------------------------------------
# These are configurable options:
# -------------------------------------------------------------------------

# 'install' program location 
INSTALL ?= install

# Location where the package is installed by 'make install' 
prefix ?= /usr/local

# Destination root (/ is used if empty) 
DESTDIR ?= 

#  
AR ?= ar

#  
RANLIB ?= ranlib

# Compiler flags to link shared library 
LINK_DLL_FLAGS ?= -shared

# C++ compiler 
CXX = g++

# Standard flags for C++ 
CXXFLAGS ?= 

# Standard preprocessor flags (common for CC and CXX) 
CPPFLAGS ?= 

# Standard linker flags 
LDFLAGS ?= 

# Set to 1 to build debug version [0,1]
DEBUG ?= 0

#  
GPIB ?= 0



# -------------------------------------------------------------------------
# Do not modify the rest of this file!
# -------------------------------------------------------------------------

### Variables: ###

CPPDEPS = -MT$@ -MF`echo $@ | sed -e 's,\.o$$,.d,'` -MD -MP
CTB_LIB_CXXFLAGS = $(____DEBUG) $(____DEBUG_1) -D_THREAD_SAFE -pthread \
	$(__OPTIMIZE_FLAG) -I../include $(CPPFLAGS) $(CXXFLAGS)
CTB_LIB_OBJECTS =  \
	$(OUTPUT)/ctb_lib_fifo.o \
	$(OUTPUT)/ctb_lib_getopt.o \
	$(OUTPUT)/ctb_lib_iobase.o \
	$(OUTPUT)/ctb_lib_portscan.o \
	$(OUTPUT)/ctb_lib_serportx.o \
	$(OUTPUT)/ctb_lib_serport.o \
	$(OUTPUT)/ctb_lib_timer.o \
	$(__GPIBSRC_OBJECTS)
CTB_DLL_CXXFLAGS = $(____DEBUG) $(____DEBUG_1) -D_THREAD_SAFE -pthread \
	$(__OPTIMIZE_FLAG) -I../include -fPIC -DPIC $(CPPFLAGS) $(CXXFLAGS)
CTB_DLL_OBJECTS =  \
	$(OUTPUT)/ctb_dll_fifo.o \
	$(OUTPUT)/ctb_dll_getopt.o \
	$(OUTPUT)/ctb_dll_iobase.o \
	$(OUTPUT)/ctb_dll_portscan.o \
	$(OUTPUT)/ctb_dll_serportx.o \
	$(OUTPUT)/ctb_dll_serport.o \
	$(OUTPUT)/ctb_dll_timer.o \
	$(__GPIBSRC_OBJECTS_1)
CTBTEST_CXXFLAGS = $(____DEBUG) $(____DEBUG_1) -DGPIB=$(GPIB) -D_THREAD_SAFE \
	-pthread $(__OPTIMIZE_FLAG) -I../include $(CPPFLAGS) $(CXXFLAGS)
CTBTEST_OBJECTS =  \
	$(OUTPUT)/ctbtest_ctbtest.o

### Conditionally set variables: ###

ifeq ($(DEBUG),0)
OUTPUT = release
endif
ifeq ($(DEBUG),1)
OUTPUT = debug
endif
ifeq ($(DEBUG),1)
LIBFLAG = d
endif
ifeq ($(GPIB),1)
GPIBFLAG = _gpib
endif
ifeq ($(GPIB),1)
GPIBINC = gpib.h
endif
ifeq ($(GPIB),1)
__GPIBSRC_OBJECTS =  \
	$(OUTPUT)/ctb_lib_gpib.o
endif
ifeq ($(GPIB),1)
__GPIBSRC_OBJECTS_1 =  \
	$(OUTPUT)/ctb_dll_gpib.o
endif
ifeq ($(DEBUG),0)
____DEBUG = -DNDEBUG
endif
ifeq ($(DEBUG),1)
____DEBUG = 
endif
ifeq ($(DEBUG),0)
__OPTIMIZE_FLAG = -O0
endif
ifeq ($(DEBUG),1)
__OPTIMIZE_FLAG = -O2
endif
ifeq ($(GPIB),1)
__SYSLIB2_p = -lgpib
endif
ifeq ($(DEBUG),0)
____DEBUG_1 = 
endif
ifeq ($(DEBUG),1)
____DEBUG_1 = -g
endif


all: $(OUTPUT)
$(OUTPUT):
	@mkdir -p $(OUTPUT)

### Targets: ###

all: ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so $(OUTPUT)/ctbtest tip-linux

install: install_ctb_lib install_ctb_dll
	$(INSTALL) -d $(DESTDIR)$(prefix)/include/ctb-0.16
	for f in ctb.h fifo.h getopt.h $(GPIBINC) iobase.h linux/serport.h linux/timer.h portscan.h serport.h serportx.h timer.h; do \
	if test ! -d $(DESTDIR)$(prefix)/include/ctb-0.16/`dirname $$f` ; then \
	$(INSTALL) -d $(DESTDIR)$(prefix)/include/ctb-0.16/`dirname $$f`; \
	fi; \
	$(INSTALL) -m 644 ../include/ctb-0.16/$$f $(DESTDIR)$(prefix)/include/ctb-0.16/$$f; \
	done

uninstall: uninstall_ctb_lib uninstall_ctb_dll
	for f in ctb.h fifo.h getopt.h $(GPIBINC) iobase.h linux/serport.h linux/timer.h portscan.h serport.h serportx.h timer.h; do \
	rm -f $(DESTDIR)$(prefix)/include/ctb-0.16/$$f; \
	done

clean: 
	rm -f $(OUTPUT)/*.o
	rm -f $(OUTPUT)/*.d
	rm -f ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a
	rm -f ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so
	rm -f ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so
	rm -f $(OUTPUT)/ctbtest

htmldoc: 
	(cd ..; tar -cvzf manual/libctb-0.16-htmldoc.tar.gz docs/html/ )

tarball: 
	(cd ../..; tar -cvzf libctb-0.16.tar.gz \
	libctb-0.16/build/ \
	libctb-0.16/manual/refman.pdf \
	libctb-0.16/include \
	libctb-0.16/python \
	libctb-0.16/samples \
	libctb-0.16/src \
	libctb-0.16/lib/gpib32.lib \
	--exclude=release \
	--exclude=debug \
	--exclude=install \
	--exclude=output \
	--exclude=website \
	--exclude=*~ \
	--exclude=buildall.sh \
	--exclude=buildall.bat \
	--exclude=version-update.sh \
	--exclude=libctb-0.16.tar.gz \
	--exclude=*.ilk \
	--exclude=*.log \
	--exclude=*.o* \
	--exclude=*.pdb \
	--exclude=*.pyc \
	--exclude=.svn; mv libctb-0.16.tar.gz libctb-0.16/build )

../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a: $(CTB_LIB_OBJECTS)
	rm -f $@
	$(AR) rcu $@ $(CTB_LIB_OBJECTS)
	$(RANLIB) $@

install_ctb_lib: ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a
	$(INSTALL) -d $(DESTDIR)$(prefix)/lib
	$(INSTALL) -m 644 ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a $(DESTDIR)$(prefix)/lib

uninstall_ctb_lib: 
	rm -f $(DESTDIR)$(prefix)/lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a

../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so: $(CTB_DLL_OBJECTS)
	$(CXX) $(LINK_DLL_FLAGS) -fPIC -o $@ $(CTB_DLL_OBJECTS)  $(____DEBUG_1) -pthread -L../lib $(LDFLAGS)  -lpthread $(__SYSLIB2_p)

install_ctb_dll: ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so
	$(INSTALL) -d $(DESTDIR)$(prefix)/lib
	$(INSTALL) -m 644 ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so $(DESTDIR)$(prefix)/lib
	install -c ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so $(DESTDIR)$(prefix)/lib

uninstall_ctb_dll: 
	rm -f $(DESTDIR)$(prefix)/lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so
	rm -f $(DESTDIR)$(prefix)/lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.so

$(OUTPUT)/ctbtest: $(CTBTEST_OBJECTS) ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a
	$(CXX) -o $@ $(CTBTEST_OBJECTS)  $(____DEBUG_1) -pthread -L../lib $(LDFLAGS)  ../lib/libctb$(LIBFLAG)$(GPIBFLAG)-0.16.a -lpthread $(__SYSLIB2_p)

tip-linux: 
	@echo " "
	@echo "================================================================"
	@echo " The building of ctb is finished. On Linux you'll now"
	@echo " have to run (as root):"
	@echo " "
	@echo " make DEBUG=$(DEBUG) GPIB=$(GPIB) install"
	@echo " "
	@echo " to install the libraries in $(prefix)/lib"
	@echo " and the header files in $(prefix)/include/ctb-0.16"
	@echo " "
	@echo " Don't forget to run ldconfig (also as root)"
	@echo " "
	@echo " ctb comes with no guarantees and doesn't claim"
	@echo " to be suitable for any purpose."
	@echo "================================================================"
	@echo " "

$(OUTPUT)/ctb_lib_fifo.o: ./../src/fifo.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_lib_getopt.o: ./../src/getopt.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_lib_iobase.o: ./../src/iobase.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_lib_portscan.o: ./../src/portscan.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_lib_serportx.o: ./../src/serportx.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_lib_serport.o: ./../src/linux/serport.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_lib_timer.o: ./../src/linux/timer.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_lib_gpib.o: ./../src/gpib.cpp
	$(CXX) -c -o $@ $(CTB_LIB_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_fifo.o: ./../src/fifo.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_getopt.o: ./../src/getopt.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_iobase.o: ./../src/iobase.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_portscan.o: ./../src/portscan.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_serportx.o: ./../src/serportx.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_serport.o: ./../src/linux/serport.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_timer.o: ./../src/linux/timer.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctb_dll_gpib.o: ./../src/gpib.cpp
	$(CXX) -c -o $@ $(CTB_DLL_CXXFLAGS) $(CPPDEPS) $<

$(OUTPUT)/ctbtest_ctbtest.o: ./../samples/ctbtest.cpp
	$(CXX) -c -o $@ $(CTBTEST_CXXFLAGS) $(CPPDEPS) $<

.PHONY: all install uninstall clean install_ctb_lib uninstall_ctb_lib \
	install_ctb_dll uninstall_ctb_dll


# Dependencies tracking:
-include $(OUTPUT)/*.d
