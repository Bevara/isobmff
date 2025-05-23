cmake_minimum_required(VERSION 3.7)
project(Filters)

include(filters.cmake)

add_definitions(-fpic)

set(CMAKE_BUILD_TYPE Release)
set(CMAKE_CXX_FLAGS "-O3 -Wall -Wextra")
set(CMAKE_C_FLAGS "-O3 -Wall -Wextra")

SET(ISOBMFF_SRC
        ${CMAKE_CURRENT_SOURCE_DIR}/av_parsers.c
        ${CMAKE_CURRENT_SOURCE_DIR}/bitstream.c
        ${CMAKE_CURRENT_SOURCE_DIR}/movie_fragments.c
        ${CMAKE_CURRENT_SOURCE_DIR}/drm_sample.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isom_write.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isoffin_read.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isoffin_load.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isoffin_read_ch.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isom_tools.c
        ${CMAKE_CURRENT_SOURCE_DIR}/mux_isom.c
        ${CMAKE_CURRENT_SOURCE_DIR}/mux_ts.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isom_read.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isom_store.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_funcs.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_code_base.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_dump.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_code_meta.c
        ${CMAKE_CURRENT_SOURCE_DIR}/avc_ext.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_code_drm.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_code_3gpp.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_code_apple.c
        ${CMAKE_CURRENT_SOURCE_DIR}/box_code_adobe.c
        ${CMAKE_CURRENT_SOURCE_DIR}/isom_intern.c
        ${CMAKE_CURRENT_SOURCE_DIR}/media_import.c
        ${CMAKE_CURRENT_SOURCE_DIR}/data_map.c
        ${CMAKE_CURRENT_SOURCE_DIR}/iff.c
        ${CMAKE_CURRENT_SOURCE_DIR}/meta.c
        ${CMAKE_CURRENT_SOURCE_DIR}/sample_descs.c
        ${CMAKE_CURRENT_SOURCE_DIR}/track.c
        ${CMAKE_CURRENT_SOURCE_DIR}/media.c
        ${CMAKE_CURRENT_SOURCE_DIR}/stbl_read.c
        ${CMAKE_CURRENT_SOURCE_DIR}/stbl_write.c
        ${CMAKE_CURRENT_SOURCE_DIR}/webvtt.c
        ${CMAKE_CURRENT_SOURCE_DIR}/reframe_nalu.c
        ${CMAKE_CURRENT_SOURCE_DIR}/media_odf.c
)

SET(ISOBMFF_INC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

add_filter(isobmff
        "${ISOBMFF_SRC}"
        ""
        []
        ""
        "${ISOBMFF_INC}"
        ""
        "1")
