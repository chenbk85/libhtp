LDADD = $(top_builddir)/htp/.libs/libhtp.a -lz @LIBICONV@ 
AM_CFLAGS = -g -std=gnu99
AM_CPPFLAGS = -I$(top_srcdir) -I$(top_builddir)/htp -Wno-write-strings -DGTEST_USE_OWN_TR1_TUPLE=1
AUTOMAKE_OPTIONS = subdir-objects
EXTRA_DIST = files
check_PROGRAMS = test_all
check_LIBRARIES = libgtest.a

test_all_SOURCES = test_bstr.cpp test_gunzip.cpp test_hybrid.cpp test_main.cpp test_multipart.cpp test.c test.h test_utils.cpp
test_all_LDADD = libgtest.a -lpthread $(LDADD)

libgtest_a_SOURCES = gtest/gtest-all.cc gtest/gtest_main.cc gtest/gtest.h

TESTS_ENVIRONMENT = srcdir=$(srcdir)/files
TESTS = test_all

test: check
	@echo

test-compile-only: all-am
	$(MAKE) $(AM_MAKEFLAGS) $(check_LIBRARIES)
	$(MAKE) $(AM_MAKEFLAGS) $(check_PROGRAMS)

check-compile-only: all-am
	$(MAKE) $(AM_MAKEFLAGS) $(check_LIBRARIES)
	$(MAKE) $(AM_MAKEFLAGS) $(check_PROGRAMS)

