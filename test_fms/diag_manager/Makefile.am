# This is an automake file for the test_fms/diag_manager directory of the FMS
# package.

LOG_DRIVER = env AM_TAP_AWK='$(AWK)' $(SHELL) \
             $(top_srcdir)/tap-driver.sh

# Build this test program.
check_PROGRAMS = test_diag_manager

# This is the source code for the test.
test_diag_manager_SOURCES = test_diag_manager.F90
test_diag_manager_LDADD = ${top_builddir}/libFMS/libFMS.la

# Find the fms_mod.mod file.
test_diag_manager_CPPFLAGS = -I${top_srcdir}/include
test_diag_manager_CPPFLAGS += -I${top_builddir}/mpp
test_diag_manager_CPPFLAGS += -I${top_builddir}/fms
test_diag_manager_CPPFLAGS += -I${top_builddir}/diag_manager
test_diag_manager_CPPFLAGS += -I${top_builddir}/time_manager
test_diag_manager_CPPFLAGS += -I${top_builddir}/constants

# Copy over other needed files to the srcdir
EXTRA_DIST = test_diag_manager.sh
EXTRA_DIST += input.nml_base
EXTRA_DIST += diagTables
EXTRA_DIST += test_diag_manager.bats

# Run the test program.
TESTS = test_diag_manager.sh

# Set srcdir as evironment variable to be reference in the job script
TESTS_ENVIRONMENT = srcdir="$(top_srcdir)"

CLEANFILES = input.nml *.nc *.out