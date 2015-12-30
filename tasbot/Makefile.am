AM_CXXFLAGS = -pthread $(PROTOBUF_CFLAGS) $(SDL_CFLAGS) $(SDL_NET_CFLAGS) \
              $(ZLIB_CFLAGS) $(LIBPNG_CFLAGS) \
              -DMARIONET=1 -I../cc-lib -I../cc-lib/city -DPSS_STYLE=1 \
              -DDUMMY_UI -DNOWINSTUFF -DHAVE_ASPRINTF -DHAVE_ALLOCA -Ifceu
AM_LDFLAGS = -pthread $(PROTOBUF_LIBS) $(SDL_LIBS) $(SDL_NET_LIBS) \
             $(ZLIB_LIBS) $(LIBPNG_LIBS)

bin_PROGRAMS = learnfun playfun scopefun pinviz
check_PROGRAMS = emu_test objective_test weighted_objectives_test

# Weird protobuf junk
%.pb.cc %.pb.h: %.proto
	$(PROTOC) --proto_path=. --cpp_out=. $^
dist_noinst_DATA = marionet.proto
MARIONETSOURCES = marionet.pb.cc marionet.pb.h
MOSTLYCLEANFILES = $(MARIONETSOURCES)
BUILT_SOURCES = marionet.pb.h

# All the fceu sources
# Excluded:
#fceu/fir/toh.c \ main()
FCEUSOURCES = fceu/drivers/common/vidblit.cpp \
	      fceu/drivers/common/hq2x.cpp \
	      fceu/drivers/common/vidblit.h \
	      fceu/drivers/common/cheat.h \
	      fceu/drivers/common/hq3x.cpp \
	      fceu/drivers/common/scale2x.h \
	      fceu/drivers/common/scale3x.cpp \
	      fceu/drivers/common/nes_ntsc_config.h \
	      fceu/drivers/common/nes_ntsc_impl.h \
	      fceu/drivers/common/cheat.cpp \
	      fceu/drivers/common/args.h \
	      fceu/drivers/common/hq3x.h \
	      fceu/drivers/common/args.cpp \
	      fceu/drivers/common/scalebit.h \
	      fceu/drivers/common/scale3x.h \
	      fceu/drivers/common/nes_ntsc.c \
	      fceu/drivers/common/hq2x.h \
	      fceu/drivers/common/scalebit.cpp \
	      fceu/drivers/common/scale2x.cpp \
	      fceu/drivers/common/nes_ntsc.h \
	      fceu/unif.cpp \
	      fceu/fds.cpp \
	      fceu/sound.cpp \
	      fceu/ppu.cpp \
	      fceu/types-des.h \
	      fceu/palettes/rp2c05004.h \
	      fceu/palettes/rp2c04002.h \
	      fceu/palettes/rp2c04001.h \
	      fceu/palettes/palettes.h \
	      fceu/palettes/rp2c04003.h \
	      fceu/filter.cpp \
	      fceu/fceulua.h \
	      fceu/input.cpp \
	      fceu/oldmovie.cpp \
	      fceu/ines.h \
	      fceu/vsuni.cpp \
	      fceu/unif.h \
	      fceu/driver.h \
	      fceu/netplay.h \
	      fceu/netplay.cpp \
	      fceu/debug.h \
	      fceu/file.cpp \
	      fceu/filter.h \
	      fceu/movie.cpp \
	      fceu/config.h \
	      fceu/debug.cpp \
	      fceu/cheat.h \
	      fceu/cart.h \
	      fceu/x6502.h \
	      fceu/cart.cpp \
	      fceu/nsf.cpp \
	      fceu/mappers/46.cpp \
	      fceu/mappers/40.cpp \
	      fceu/mappers/67.cpp \
	      fceu/mappers/75.cpp \
	      fceu/mappers/mapinc.h \
	      fceu/mappers/24and26.cpp \
	      fceu/mappers/71.cpp \
	      fceu/mappers/69.cpp \
	      fceu/mappers/73.cpp \
	      fceu/mappers/51.cpp \
	      fceu/mappers/65.cpp \
	      fceu/mappers/6.cpp \
	      fceu/mappers/61.cpp \
	      fceu/mappers/mmc2and4.cpp \
	      fceu/mappers/79.cpp \
	      fceu/mappers/41.cpp \
	      fceu/mappers/50.cpp \
	      fceu/mappers/emu2413.c \
	      fceu/mappers/85.cpp \
	      fceu/mappers/72.cpp \
	      fceu/mappers/62.cpp \
	      fceu/mappers/80.cpp \
	      fceu/mappers/42.cpp \
	      fceu/mappers/emu2413.h \
	      fceu/mappers/76.cpp \
	      fceu/mappers/77.cpp \
	      fceu/config.cpp \
	      fceu/emufile_types.h \
	      fceu/git.h \
	      fceu/asm.cpp \
	      fceu/x6502.cpp \
	      fceu/types.h \
	      fceu/drawing.cpp \
	      fceu/version.h \
	      fceu/palette.cpp \
	      fceu/cheat.cpp \
	      fceu/movie.h \
	      fceu/ppu.h \
	      fceu/drawing.h \
	      fceu/conddebug.h \
	      fceu/fds.h \
	      fceu/nsf.h \
	      fceu/ines-correct.h \
	      fceu/palette.h \
	      fceu/conddebug.cpp \
	      fceu/emufile.h \
	      fceu/state.cpp \
	      fceu/asm.h \
	      fceu/sound.h \
	      fceu/emufile.cpp \
	      fceu/ines-bad.h \
	      fceu/utils/crc32.cpp \
	      fceu/utils/endian.cpp \
	      fceu/utils/unzip.cpp \
	      fceu/utils/valuearray.h \
	      fceu/utils/memory.h \
	      fceu/utils/crc32.h \
	      fceu/utils/ConvertUTF.c \
	      fceu/utils/ConvertUTF.h \
	      fceu/utils/unzip.h \
	      fceu/utils/endian.h \
	      fceu/utils/guid.cpp \
	      fceu/utils/memory.cpp \
	      fceu/utils/xstring.cpp \
	      fceu/utils/xstring.h \
	      fceu/utils/general.cpp \
	      fceu/utils/guid.h \
	      fceu/utils/md5.h \
	      fceu/utils/general.h \
	      fceu/utils/md5.cpp \
	      fceu/wave.cpp \
	      fceu/oldmovie.h \
	      fceu/input/oekakids.cpp \
	      fceu/input/toprider.cpp \
	      fceu/input/fkb.h \
	      fceu/input/share.h \
	      fceu/input/shadow.cpp \
	      fceu/input/zapper.h \
	      fceu/input/ftrainer.cpp \
	      fceu/input/arkanoid.cpp \
	      fceu/input/cursor.cpp \
	      fceu/input/zapper.cpp \
	      fceu/input/hypershot.cpp \
	      fceu/input/mahjong.cpp \
	      fceu/input/powerpad.cpp \
	      fceu/input/mouse.cpp \
	      fceu/input/quiz.cpp \
	      fceu/input/suborkb.cpp \
	      fceu/input/suborkb.h \
	      fceu/input/bworld.cpp \
	      fceu/input/fkb.cpp \
	      fceu/input.h \
	      fceu/fir/c48000ntsc.h \
	      fceu/fir/c96000ntsc.h \
	      fceu/fir/c48000pal.h \
	      fceu/fir/c44100pal.h \
	      fceu/fir/c96000pal.h \
	      fceu/fir/c44100ntsc.h \
	      fceu/video.h \
	      fceu/file.h \
	      fceu/state.h \
	      fceu/wave.h \
	      fceu/video.cpp \
	      fceu/fceu.h \
	      fceu/x6502struct.h \
	      fceu/boards/175.cpp \
	      fceu/boards/244.cpp \
	      fceu/boards/supervision.cpp \
	      fceu/boards/68.cpp \
	      fceu/boards/gs-2013.cpp \
	      fceu/boards/smb2j.cpp \
	      fceu/boards/116.cpp \
	      fceu/boards/95.cpp \
	      fceu/boards/187.cpp \
	      fceu/boards/n-c22m.cpp \
	      fceu/boards/bmc42in1r.cpp \
	      fceu/boards/addrlatch.cpp \
	      fceu/boards/mmc3.h \
	      fceu/boards/90.cpp \
	      fceu/boards/dream.cpp \
	      fceu/boards/subor.cpp \
	      fceu/boards/230.cpp \
	      fceu/boards/234.cpp \
	      fceu/boards/konami-qtai.cpp \
	      fceu/boards/252.cpp \
	      fceu/boards/170.cpp \
	      fceu/boards/bandai.cpp \
	      fceu/boards/8237.cpp \
	      fceu/boards/vrc7.cpp \
	      fceu/boards/193.cpp \
	      fceu/boards/33.cpp \
	      fceu/boards/__dummy_mapper.cpp \
	      fceu/boards/deirom.cpp \
	      fceu/boards/mmc5.cpp \
	      fceu/boards/830118C.cpp \
	      fceu/boards/tengen.cpp \
	      fceu/boards/232.cpp \
	      fceu/boards/ks7031.cpp \
	      fceu/boards/112.cpp \
	      fceu/boards/ax5705.cpp \
	      fceu/boards/253.cpp \
	      fceu/boards/bmc64in1nr.cpp \
	      fceu/boards/gs-2004.cpp \
	      fceu/boards/bmc13in1jy110.cpp \
	      fceu/boards/mapinc.h \
	      fceu/boards/lh32.cpp \
	      fceu/boards/sa-9602b.cpp \
	      fceu/boards/178.cpp \
	      fceu/boards/186.cpp \
	      fceu/boards/164.cpp \
	      fceu/boards/mmc3.cpp \
	      fceu/boards/17.cpp \
	      fceu/boards/176.cpp \
	      fceu/boards/15.cpp \
	      fceu/boards/datalatch.cpp \
	      fceu/boards/edu2000.cpp \
	      fceu/boards/108.cpp \
	      fceu/boards/transformer.cpp \
	      fceu/boards/222.cpp \
	      fceu/boards/kof97.cpp \
	      fceu/boards/novel.cpp \
	      fceu/boards/onebus.cpp \
	      fceu/boards/208.cpp \
	      fceu/boards/bmc70in1.cpp \
	      fceu/boards/18.cpp \
	      fceu/boards/n106.cpp \
	      fceu/boards/96.cpp \
	      fceu/boards/ac-08.cpp \
	      fceu/boards/88.cpp \
	      fceu/boards/cityfighter.cpp \
	      fceu/boards/91.cpp \
	      fceu/boards/43.cpp \
	      fceu/boards/ks7017.cpp \
	      fceu/boards/121.cpp \
	      fceu/boards/603-5052.cpp \
	      fceu/boards/tf-1201.cpp \
	      fceu/boards/99.cpp \
	      fceu/boards/225.cpp \
	      fceu/boards/82.cpp \
	      fceu/boards/106.cpp \
	      fceu/boards/ks7030.cpp \
	      fceu/boards/le05.cpp \
	      fceu/boards/sc-127.cpp \
	      fceu/boards/n625092.cpp \
	      fceu/boards/sl1632.cpp \
	      fceu/boards/a9746.cpp \
	      fceu/boards/ks7057.cpp \
	      fceu/boards/32.cpp \
	      fceu/boards/pec-586.cpp \
	      fceu/boards/34.cpp \
	      fceu/boards/dance2000.cpp \
	      fceu/boards/3d-block.cpp \
	      fceu/boards/bs-5.cpp \
	      fceu/boards/151.cpp \
	      fceu/boards/t-227-1.cpp \
	      fceu/boards/246.cpp \
	      fceu/boards/28.cpp \
	      fceu/boards/lh53.cpp \
	      fceu/boards/yoko.cpp \
	      fceu/boards/super24.cpp \
	      fceu/boards/12in1.cpp \
	      fceu/boards/156.cpp \
	      fceu/boards/t-262.cpp \
	      fceu/boards/189.cpp \
	      fceu/boards/8157.cpp \
	      fceu/boards/mmc1.cpp \
	      fceu/boards/ghostbusters63in1.cpp \
	      fceu/boards/karaoke.cpp \
	      fceu/boards/h2288.cpp \
	      fceu/boards/a9711.cpp \
	      fceu/boards/bonza.cpp \
	      fceu/boards/103.cpp \
	      fceu/boards/199.cpp \
	      fceu/boards/famicombox.cpp \
	      fceu/boards/sheroes.cpp \
	      fceu/boards/vrc2and4.cpp \
	      fceu/boards/117.cpp \
	      fceu/boards/bb.cpp \
	      fceu/boards/fk23c.cpp \
	      fceu/boards/411120-c.cpp \
	      fceu/boards/177.cpp \
	      fceu/boards/185.cpp \
	      fceu/boards/168.cpp \
	      fceu/boards/malee.cpp \
	      fceu/boards/ks7013.cpp \
	      fceu/boards/ks7037.cpp \
	      fceu/boards/120.cpp \
	      fceu/boards/228.cpp \
	      fceu/boards/ks7032.cpp \
	      fceu/boards/57.cpp \
	      fceu/boards/179.cpp \
	      fceu/boards/ks7012.cpp \
	      fceu/boards/235.cpp \
	      fceu/boards/01-222.cpp \
	      fceu/boards/sachen.cpp \
	      fceu/boards/183.cpp \
	      fceu/vsuni.h \
	      fceu/fcoeffs.h \
	      fceu/x6502abbrev.h \
	      fceu/ines.cpp \
	      fceu/fceu.cpp \
	      fceu/pputile.inc \
	      fceu/ops.inc

TASBOTSOURCES = headless-driver.cc \
		simplefm2.cc \
		emulator.cc \
		emulator.h \
		basis-util.cc \
		basis-util.h \
		objective.cc \
		weighted-objectives.cc \
		motifs.cc \
		util.cc \
		game.h \
		motifs-style.h \
		motifs.h \
		sdlutil-lite.h \
		simplefm2.h \
		tasbot.h \
		util.h \
		wave.h \
		weighted-objectives.h \
		objective.h

NETWORKINGSOURCES = netutil.cc netutil.h

PNGSAVESOURCES = pngsave.cc pngsave.h

COMMON_SOURCES = $(FCEUSOURCES) $(TASBOTSOURCES) $(NETWORKINGSOURCES)

# The actual sources
learnfun_SOURCES = $(COMMON_SOURCES) learnfun.cc
nodist_learnfun_SOURCES = $(MARIONETSOURCES)
learnfun_LDADD = ../cc-lib/libcclib.la

playfun_SOURCES = $(COMMON_SOURCES) playfun.cc
nodist_playfun_SOURCES = $(MARIONETSOURCES)
playfun_LDADD = ../cc-lib/libcclib.la

scopefun_SOURCES = $(COMMON_SOURCES) $(PNGSAVESOURCES) scopefun.cc wave.cc
nodist_scopefun_SOURCES = $(MARIONETSOURCES)
scopefun_LDADD = ../cc-lib/libcclib.la

pinviz_SOURCES = $(COMMON_SOURCES) $(PNGSAVESOURCES) pinviz.cc wave.cc
nodist_pinviz_SOURCES = $(MARIONETSOURCES)
pinviz_LDADD = ../cc-lib/libcclib.la

# Tests
emu_test_SOURCES = $(COMMON_SOURCES) emu_test.cc
nodist_emu_test_SOURCES = $(MARIONETSOURCES)
emu_test_LDADD = ../cc-lib/libcclib.la

objective_test_SOURCES = $(COMMON_SOURCES) objective_test.cc
nodist_objective_test_SOURCES = $(MARIONETSOURCES)
objective_test_LDADD = ../cc-lib/libcclib.la

weighted_objectives_test_SOURCES = $(COMMON_SOURCES) weighted-objectives_test.cc
nodist_weighted_objectives_test_SOURCES = $(MARIONETSOURCES)
weighted_objectives_test_LDADD = ../cc-lib/libcclib.la

XFAIL_TESTS = emu_test
TESTS = $(check_PROGRAMS)
