CXX=icpc
CXXFLAGS=-O3 -std=c++11 -g -I$(VTUNE_HOME)/include
LDFLAGS=-L$(VTUNE_HOME)/lib64
LIBS=-littnotify
SHARED_CXXFLAGS=-shared -fPIC

all: kp_vtune_focused_connector.so

MAKEFILE_PATH := $(subst Makefile,,$(abspath $(lastword $(MAKEFILE_LIST))))

CXXFLAGS+=-I${MAKEFILE_PATH} -I${MAKEFILE_PATH}/../../common/makefile-only -I${MAKEFILE_PATH}../all

kp_vtune_focused_connector.so: ${MAKEFILE_PATH}kp_vtune_focused_connector.cpp ${MAKEFILE_PATH}kp_vtune_focused_connector_domain.h
	$(CXX) $(SHARED_CXXFLAGS) $(CXXFLAGS) $(LDFLAGS) \
		-o $@ ${MAKEFILE_PATH}kp_vtune_focused_connector.cpp $(LIBS)

clean:
	rm *.so
