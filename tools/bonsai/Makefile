SHELL = /bin/sh
NAME = all
MAKEFILE = Makefile

# Include machine specific flags and locations (inc. files & libs)
#
#include $(RATROOT)/src/make/Make.include

##BONSAI_LIBS  = $(shell $(GENIE)/src/scripts/setup/genie-config --libs)
RAT_LIBS = -L$(RATROOT)/lib -lRATEvent
ROOT_FLAG = `root-config --cflags --libs`


LIBRARIES  := $(LIBRARIES) $(CERN_LIBRARIES) $(RAT_LIBS)

INCLUDES := $(INCLUDES) -I$(RATROOT)/include -I$(RATROOT)/src/fit/bonsai

all: bonsai

bonsai: FORCE
	$(CXX) -g $(ROOT_FLAG) -o bonsai $(CXXFLAGS) $(LDFLAGS) bonsai.cc $(INCLUDES) $(LIBRARIES)

#################### CLEANING

purge: FORCE
	$(RM) *.o *~ core

clean: FORCE
	$(RM) *.o *~ core
	$(RM) bonsai

dumbway: FORCE
	g++ `root-config --cflags --libs` -g -o bonsai   bonsai.cc  -I/Users/bergevin1/software/rat-pac/include   -L/Users/bergevin1/software/rat-pac/lib -lRATEvent -lrat -I/Users/bergevin1/software/rat-pac/src/fit/bonsai/
FORCE:

# DO NOT DELETE
