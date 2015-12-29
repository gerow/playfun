SUBDIRS = base

AM_CXXFLAGS = -pthread
AM_LDFLAGS  = -pthread

check_PROGRAMS = heap_test rle_test interval_tree_test threadutil_test
noinst_LTLIBRARIES = libcclib.la

# This dir
libcclib_la_SOURCES = arcfour.cc arcfour.h \
		      color-util.cc color-util.h \
		      heap.h \
		      interval-tree.h interval-tree-json.h \
		      mingw.mutex.h mingw.thread.h \
		      randutil.h \
		      rle.h rle.cc \
		      stb_image.h stb_image.cc \
		      stb_image_write.h stb_image_write.cc \
		      stb_truetype.h stb_truetype.h \
		      textsvg.h textsvg.cc \
		      threadutil.h \
		      timer.h \
		      util.h util.cc \
		      wavesave.h wavesave.cc \
		      basictypes.h \
		      casts.h \
		      base/basictypes.h \
		      base/casts.h \
		      base/commandlineflags.h \
		      base/docid.h \
		      base/int128.cc \
		      base/int128.h \
		      base/integral_types.h \
		      base/logging.cc \
		      base/logging.h \
		      base/macros.h \
		      base/port.h \
		      base/scoped_ptr.h \
		      base/stl_decl.h \
		      base/stl_decl_msvc.h \
		      base/stl_decl_osx.h \
		      base/stringprintf.cc \
		      base/stringprintf.h \
		      base/strtoint.cc \
		      base/strtoint.h \
		      base/template_util.h \
		      base/type_traits.h

heap_test_SOURCES = heap_test.cc
heap_test_LDADD = libcclib.la

rle_test_SOURCES = rle_test.cc
rle_test_LDADD = libcclib.la

interval_tree_test_SOURCES = interval-tree_test.cc
interval_tree_test_LDADD = libcclib.la

threadutil_test_SOURCES = threadutil_test.cc
threadutil_test_LDADD = libcclib.la

TESTS = $(check_PROGRAMS)
