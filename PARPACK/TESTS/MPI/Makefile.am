F77 = $(MPIF77)
LDADD = $(top_builddir)/PARPACK/SRC/MPI/libparpack$(LIBSUFFIX).la $(LAPACK_LIBS) $(BLAS_LIBS)

# Run MPI tests with "mpirun -n 2"
LOG_COMPILER = mpirun
LOG_FLAGS = -n 2

SISS = issue46

check_PROGRAMS = $(SISS)
if ICB
check_PROGRAMS += icb_parpack_c
check_PROGRAMS += icb_parpack_cpp
endif

EXTRA_DIST = debug.h stat.h

issue46_SOURCES= issue46.f

if ICB
icb_parpack_c_SOURCES = icb_parpack_c.c
icb_parpack_c_LDADD = $(LDADD) $(MPI_C_LIBS)
icb_parpack_c_CFLAGS = -I$(top_builddir)

icb_parpack_cpp_SOURCES = icb_parpack_cpp.cpp
icb_parpack_cpp_LDADD = $(LDADD) $(MPI_CXX_LIBS)
icb_parpack_cpp_CPPFLAGS = -I$(top_builddir)
endif

TESTS = $(check_PROGRAMS)
