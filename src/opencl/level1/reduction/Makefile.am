if BUILD_MPI
    MAYBE_MPI = epmpi tpmpi
endif
SUBDIRS = $(MAYBE_MPI)

include $(top_builddir)/config/config.mk
include $(top_builddir)/config/targets.mk

# How to find source files
VPATH = $(srcdir):$(srcdir)/../../common:$(srcdir)/../../../common

AM_LDFLAGS = $(OCL_LDFLAGS)
CPPFLAGS += $(OCL_CPPFLAGS)
L1LIBS = $(OCL_LIBS) $(LIBS)

# what is the destination for programs built from this directory?
serialopencldir = $(bindir)/Serial/OpenCL

# what programs should be installed in the destination?
serialopencl_PROGRAMS = Reduction

# how to build those programs
Reduction_SOURCES = Reduction.cpp \
				reduction_cl.cpp \
                main.cpp
Reduction_LDADD   = $(L1LIBS)

