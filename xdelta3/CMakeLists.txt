cmake_minimum_required(VERSION 3.18)
project(xdelta3 C)

set (SRC
    xdelta3-blkcache.h
    xdelta3-decode.h
    xdelta3-djw.h
    xdelta3-fgk.h
    xdelta3-hash.h
    xdelta3-internal.h
    xdelta3-list.h
    xdelta3-lzma.h
    xdelta3-main.h
    xdelta3-merge.h
    xdelta3-second.h
    xdelta3-test.h
    xdelta3-cfgs.h
    xdelta3.h
    xdelta3.c
)

add_library(xdelta3 STATIC ${SRC})
# target_include_directories(hmm PUBLIC include)

target_compile_definitions(xdelta3
    PUBLIC SIZEOF_SIZE_T=8
    PUBLIC SECONDARY_LZMA=0
    PUBLIC LZMA_API_STATIC
    PUBLIC SIZEOF_UNSIGNED_LONG_LONG=8
)

# set_property(TARGET xdelta3 PROPERTY CXX_STANDARD 20)
