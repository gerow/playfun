AM_CXXFLAGS = -pthread $(PROTOBUF_CFLAGS)
AM_LDFLAGS = $(PROTOBUF_LIBS)

bin_PROGRAMS = playfun

%.pb.cc %.pb.h: %.proto
	$(PROTOC) --proto_path=. --cpp_out=. $^

dist_noinst_DATA = marionet.proto
nodist_playfun_SOURCES = marionet.pb.cc marionet.pb.h
MOSTLYCLEANFILES = marionet.pb.cc marionet.pb.h
BUILT_SOURCES = marionet.pb.h
