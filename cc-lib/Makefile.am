AM_CXXFLAGS = -pthread -Icity $(SDL_CFLAGS)
AM_LDFLAGS  = -pthread $(SDL_LIBS)

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
		      base/type_traits.h \
		      city/city.cc \
		      city/city.h \
		      city/citycrc.h \
		      jdksmidi/jdksmidi_filewrite.cpp \
		      jdksmidi/jdksmidi_midi.cpp \
		      jdksmidi/jdksmidi_filewritemultitrack.cpp \
		      jdksmidi/jdksmidi_advancedsequencer.cpp \
		      jdksmidi/jdksmidi_fileshow.cpp \
		      jdksmidi/jdksmidi_sequencer.cpp \
		      jdksmidi/jdksmidi_fileread.cpp \
		      jdksmidi/jdksmidi_matrix.cpp \
		      jdksmidi/examples/jdksmidi_test_sequencer.cpp \
		      jdksmidi/examples/jdksmidi_test_parse.cpp \
		      jdksmidi/examples/vrm_music_gen.cpp \
		      jdksmidi/examples/create_midifile.cpp \
		      jdksmidi/examples/jdksmidi_test_multitrack1.cpp \
		      jdksmidi/examples/jdksmidi_test_show.cpp \
		      jdksmidi/examples/jdksmidi_test_multitrack.cpp \
		      jdksmidi/examples/jdksmidi_test_drv.cpp \
		      jdksmidi/examples/jdksmidi_rewrite_midifile.cpp \
		      jdksmidi/examples/win32/jdksmidi_test_drvwin32.cpp \
		      jdksmidi/examples/rewrite_midifile.cpp \
		      jdksmidi/jdksmidi_tempo.cpp \
		      jdksmidi/jdksmidi_smpte.cpp \
		      jdksmidi/jdksmidi_sysex.cpp \
		      jdksmidi/jdksmidi_showcontrolhandler.cpp \
		      jdksmidi/jdksmidi_keysig.cpp \
		      jdksmidi/jdksmidi_utils.cpp \
		      jdksmidi/jdksmidi_multitrack.cpp \
		      jdksmidi/jdksmidi_showcontrol.cpp \
		      jdksmidi/jdksmidi_queue.cpp \
		      jdksmidi/jdksmidi_track.cpp \
		      jdksmidi/jdksmidi_driverdump.cpp \
		      jdksmidi/jdksmidi_manager.cpp \
		      jdksmidi/jdksmidi_filereadmultitrack.cpp \
		      jdksmidi/jdksmidi_file.cpp \
		      jdksmidi/jdksmidi_process.cpp \
		      jdksmidi/jdksmidi_parser.cpp \
		      jdksmidi/jdksmidi_msg.cpp \
		      jdksmidi/jdksmidi_driver.cpp \
		      jdksmidi/jdksmidi_edittrack.cpp \
		      jdksmidi/jdksmidi_tick.cpp \
		      jdksmidi/edittrack.h \
		      jdksmidi/jdksmidi_fileshow.cpp \
		      jdksmidi/driver.h \
		      jdksmidi/parser.h \
		      jdksmidi/filereadmultitrack.h \
		      jdksmidi/processor.h \
		      jdksmidi/driverwin32.h \
		      jdksmidi/tempo.h \
		      jdksmidi/examples/jdksmidi_test_show.cpp \
		      jdksmidi/driverdump.h \
		      jdksmidi/showcontrol.h \
		      jdksmidi/advancedsequencer.h \
		      jdksmidi/song.h \
		      jdksmidi/track.h \
		      jdksmidi/midi.h \
		      jdksmidi/msg.h \
		      jdksmidi/multitrack.h \
		      jdksmidi/jdksmidi_showcontrolhandler.cpp \
		      jdksmidi/showcontrolhandler.h \
		      jdksmidi/filewritemultitrack.h \
		      jdksmidi/jdksmidi_showcontrol.cpp \
		      jdksmidi/matrix.h \
		      jdksmidi/keysig.h \
		      jdksmidi/queue.h \
		      jdksmidi/fileread.h \
		      jdksmidi/manager.h \
		      jdksmidi/world.h \
		      jdksmidi/file.h \
		      jdksmidi/filewrite.h \
		      jdksmidi/sysex.h \
		      jdksmidi/fileshow.h \
		      jdksmidi/sequencer.h \
		      jdksmidi/tick.h \
		      jdksmidi/utils.h \
		      jdksmidi/smpte.h \
		      sdl/chars.h \
		      sdl/font.cc \
		      sdl/font.h \
		      sdl/sdlutil.cc \
		      sdl/sdlutil.h \
		      strings/stringprintf.cc \
		      strings/stringprintf.h

heap_test_SOURCES = heap_test.cc
heap_test_LDADD = libcclib.la

rle_test_SOURCES = rle_test.cc
rle_test_LDADD = libcclib.la

interval_tree_test_SOURCES = interval-tree_test.cc
interval_tree_test_LDADD = libcclib.la

threadutil_test_SOURCES = threadutil_test.cc
threadutil_test_LDADD = libcclib.la

TESTS = $(check_PROGRAMS)
