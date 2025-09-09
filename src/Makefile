PB_SRC_DIR=$(HOME)/libprotobuf-mutator-asn1/src

CXX=clang++-14
CXXFLAGS=-I$(PB_SRC_DIR)

AFL_DIR=$(HOME)/AFLplusplus
AFLCC=$(HOME)/AFLplusplus/afl-gcc

PROTOBUF_DIR=$(HOME)/libprotobuf-mutator/build/external.protobuf
PROTOBUF_LIB=$(PROTOBUF_DIR)/lib/libprotobufd.a

LPM_DIR=$(HOME)/libprotobuf-mutator
LPM_LIB=$(LPM_DIR)/build/src/libprotobuf-mutator.a

INC=-I$(PROTOBUF_DIR)/include -I$(LPM_DIR) -I$(AFL_DIR)/include -I.

all: protobuf_to_der

protobuf_to_der: protobuf_to_der.cpp common.cc x509_certificate_to_der.cc asn1_pdu.pb.cc asn1_universal_types.pb.cc asn1_universal_types_to_der.cc asn1_pdu_to_der.cc x509_certificate.pb.cc
	$(CXX) -o protobuf_to_der protobuf_to_der.cpp common.cc x509_certificate_to_der.cc asn1_pdu.pb.cc asn1_universal_types.pb.cc asn1_universal_types_to_der.cc asn1_pdu_to_der.cc x509_certificate.pb.cc $(INC) $(LPM_LIB) $(PROTOBUF_LIB)

.PHONY: clean
clean: 
	rm *.so *.o
