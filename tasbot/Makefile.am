AM_CXXFLAGS = -pthread $(PROTOBUF_CFLAGS) $(SDL_CFLAGS) $(SDL_NET_CFLAGS) \
              $(ZLIB_CFLAGS) \
              -DMARIONET=1 -I../cc-lib -I../cc-lib/city -DPSS_STYLE=1 \
              -DDUMMY_UI -DNOWINSTUFF -DHAVE_ASPRINTF -DHAVE_ALLOCA
AM_LDFLAGS = -pthread $(PROTOBUF_LIBS) $(SDL_LIBS) $(SDL_NET_LIBS) \
             $(ZLIB_LIBS)

bin_PROGRAMS = playfun

# Weird protobuf junk
%.pb.cc %.pb.h: %.proto
	$(PROTOC) --proto_path=. --cpp_out=. $^
dist_noinst_DATA = marionet.proto
nodist_playfun_SOURCES = marionet.pb.cc marionet.pb.h
MOSTLYCLEANFILES = marionet.pb.cc marionet.pb.h
BUILT_SOURCES = marionet.pb.h

# Everything's mostly normal again... well, except for these lines of objects
# copied directly from makefile.cpprig
FCEUSOURCES=fceu/asm.cpp fceu/cart.cpp fceu/cheat.cpp fceu/conddebug.cpp fceu/config.cpp fceu/debug.cpp fceu/drawing.cpp fceu/emufile.cpp fceu/fceu.cpp fceu/fds.cpp fceu/file.cpp fceu/filter.cpp fceu/ines.cpp fceu/input.cpp fceu/movie.cpp fceu/netplay.cpp fceu/nsf.cpp fceu/oldmovie.cpp fceu/palette.cpp fceu/ppu.cpp fceu/sound.cpp fceu/state.cpp fceu/unif.cpp fceu/video.cpp fceu/vsuni.cpp fceu/wave.cpp fceu/x6502.cpp

MAPPERSOURCES=fceu/mappers/24and26.cpp fceu/mappers/51.cpp fceu/mappers/69.cpp fceu/mappers/77.cpp fceu/mappers/40.cpp fceu/mappers/6.cpp fceu/mappers/71.cpp fceu/mappers/79.cpp fceu/mappers/41.cpp fceu/mappers/61.cpp fceu/mappers/72.cpp fceu/mappers/80.cpp fceu/mappers/42.cpp fceu/mappers/62.cpp fceu/mappers/73.cpp fceu/mappers/85.cpp fceu/mappers/46.cpp fceu/mappers/65.cpp fceu/mappers/75.cpp fceu/mappers/emu2413.c fceu/mappers/50.cpp fceu/mappers/67.cpp fceu/mappers/76.cpp fceu/mappers/mmc2and4.cpp

# utils/unzip.cpp removed -- needs lz
UTILSSOURCES=fceu/utils/ConvertUTF.cpp fceu/utils/general.cpp fceu/utils/memory.cpp fceu/utils/crc32.cpp fceu/utils/guid.cpp fceu/utils/endian.cpp fceu/utils/md5.cpp fceu/utils/xstring.cpp fceu/utils/unzip.cpp

# makefile.cpprig references a PALLETESOBJECTS var that I have yet to find.
# Here's hoping it isn't important!

BOARDSSOURCES=fceu/boards/01-222.cpp fceu/boards/32.cpp fceu/boards/gs-2013.cpp fceu/boards/103.cpp fceu/boards/33.cpp fceu/boards/h2288.cpp fceu/boards/106.cpp fceu/boards/34.cpp fceu/boards/karaoke.cpp fceu/boards/108.cpp fceu/boards/3d-block.cpp fceu/boards/kof97.cpp fceu/boards/112.cpp fceu/boards/411120-c.cpp fceu/boards/konami-qtai.cpp fceu/boards/116.cpp fceu/boards/43.cpp fceu/boards/ks7012.cpp fceu/boards/117.cpp fceu/boards/57.cpp fceu/boards/ks7013.cpp fceu/boards/120.cpp fceu/boards/603-5052.cpp fceu/boards/ks7017.cpp fceu/boards/121.cpp fceu/boards/68.cpp fceu/boards/ks7030.cpp fceu/boards/12in1.cpp fceu/boards/8157.cpp fceu/boards/ks7031.cpp fceu/boards/15.cpp fceu/boards/82.cpp fceu/boards/ks7032.cpp fceu/boards/151.cpp fceu/boards/8237.cpp fceu/boards/ks7037.cpp fceu/boards/156.cpp fceu/boards/830118C.cpp fceu/boards/ks7057.cpp fceu/boards/164.cpp fceu/boards/88.cpp fceu/boards/le05.cpp fceu/boards/168.cpp fceu/boards/90.cpp fceu/boards/lh32.cpp fceu/boards/17.cpp fceu/boards/91.cpp fceu/boards/lh53.cpp fceu/boards/170.cpp fceu/boards/95.cpp fceu/boards/malee.cpp fceu/boards/175.cpp fceu/boards/96.cpp fceu/boards/mmc1.cpp fceu/boards/176.cpp fceu/boards/99.cpp fceu/boards/mmc3.cpp fceu/boards/177.cpp fceu/boards/__dummy_mapper.cpp fceu/boards/mmc5.cpp fceu/boards/178.cpp fceu/boards/a9711.cpp fceu/boards/n-c22m.cpp fceu/boards/179.cpp fceu/boards/a9746.cpp fceu/boards/n106.cpp fceu/boards/18.cpp fceu/boards/ac-08.cpp fceu/boards/n625092.cpp fceu/boards/183.cpp fceu/boards/addrlatch.cpp fceu/boards/novel.cpp fceu/boards/185.cpp fceu/boards/ax5705.cpp fceu/boards/onebus.cpp fceu/boards/186.cpp fceu/boards/bandai.cpp fceu/boards/pec-586.cpp fceu/boards/187.cpp fceu/boards/bb.cpp fceu/boards/sa-9602b.cpp fceu/boards/189.cpp fceu/boards/bmc13in1jy110.cpp fceu/boards/sachen.cpp fceu/boards/193.cpp fceu/boards/bmc42in1r.cpp fceu/boards/sc-127.cpp fceu/boards/199.cpp fceu/boards/bmc64in1nr.cpp fceu/boards/sheroes.cpp fceu/boards/208.cpp fceu/boards/bmc70in1.cpp fceu/boards/sl1632.cpp fceu/boards/222.cpp fceu/boards/bonza.cpp fceu/boards/smb2j.cpp fceu/boards/225.cpp fceu/boards/bs-5.cpp fceu/boards/subor.cpp fceu/boards/228.cpp fceu/boards/cityfighter.cpp fceu/boards/super24.cpp fceu/boards/230.cpp fceu/boards/dance2000.cpp fceu/boards/supervision.cpp fceu/boards/232.cpp fceu/boards/datalatch.cpp fceu/boards/t-227-1.cpp fceu/boards/234.cpp fceu/boards/deirom.cpp fceu/boards/t-262.cpp fceu/boards/235.cpp fceu/boards/dream.cpp fceu/boards/tengen.cpp fceu/boards/244.cpp fceu/boards/edu2000.cpp fceu/boards/tf-1201.cpp fceu/boards/246.cpp fceu/boards/famicombox.cpp fceu/boards/transformer.cpp fceu/boards/252.cpp fceu/boards/fk23c.cpp fceu/boards/vrc2and4.cpp fceu/boards/253.cpp fceu/boards/ghostbusters63in1.cpp fceu/boards/vrc7.cpp fceu/boards/28.cpp fceu/boards/gs-2004.cpp fceu/boards/yoko.cpp


INPUTSOURCES=fceu/input/arkanoid.cpp fceu/input/ftrainer.cpp fceu/input/oekakids.cpp fceu/input/suborkb.cpp fceu/input/bworld.cpp fceu/input/hypershot.cpp fceu/input/powerpad.cpp fceu/input/toprider.cpp fceu/input/cursor.cpp fceu/input/mahjong.cpp fceu/input/quiz.cpp fceu/input/zapper.cpp fceu/input/fkb.cpp fceu/input/mouse.cpp fceu/input/shadow.cpp

# fceu/drivers/common/config.cpp fceu/drivers/common/configSys.cpp
DRIVERS_COMMON_SOURCES=fceu/drivers/common/args.cpp fceu/drivers/common/nes_ntsc.cpp fceu/drivers/common/cheat.cpp fceu/drivers/common/scale2x.cpp  fceu/drivers/common/scale3x.cpp fceu/drivers/common/scalebit.cpp fceu/drivers/common/hq2x.cpp fceu/drivers/common/vidblit.cpp fceu/drivers/common/hq3x.cpp

EMUSOURCES=$(FCEUSOURCES) $(MAPPERSOURCES) $(UTILSSOURCES) $(PALLETESOBJECTS) $(BOARDSSOURCES) $(INPUTSOURCES) $(DRIVERS_COMMON_SOURCES)

TASBOTSOURCES=headless-driver.cc simplefm2.cc emulator.cc basis-util.cc objective.cc weighted-objectives.cc motifs.cpp util.cc

NETWORKINGSOURCES = netutil.cc

COMMON_SOURCES = $(EMUSOURCES) $(TASBOTSOURCES) $(NETWORKINGSOURCES)

# The actual sources
playfun_SOURCES = $(COMMON_SOURCES) playfun.cc
playfun_LDADD = ../cc-lib/libcclib.la
