# Recommendations from https://tech.davis-hansson.com/p/make/.
SHELL := bash
.ONESHELL:
.SHELLFLAGS := -eu -o pipefail -c
.DELETE_ON_ERROR:
.PHONY: all clean
MAKEFLAGS += --warn-undefined-variables
MAKEFLAGS += --no-builtin-rules

all: Out/WebView2Loader.dll

clean:
	@rm -rf Out/WebView2Loader.dll Out/WebView2Loader.o

Out/WebView2Loader.dll: Out/WebView2Loader.o
	$(CXX) -static -static-libstdc++ -shared Out/WebView2Loader.o -lole32 -lversion -Os -s -o $@

Out/WebView2Loader.o: Source/WebView2Loader.cpp
	$(CXX) -c Source/WebView2Loader.cpp -O3 -o $@
