cmake_minimum_required(VERSION 3.7)
project(Filters)

include(filters.cmake)

add_definitions(-fpic)

SET(ISOBMFF_SRC
        ${CMAKE_SOURCE_DIR}/isoffin_read.c
        ${CMAKE_SOURCE_DIR}/isoffin_load.c
        ${CMAKE_SOURCE_DIR}/isoffin_read_ch.c
        ${CMAKE_SOURCE_DIR}/isom_tools.c
        ${CMAKE_SOURCE_DIR}/mux_isom.c
        ${CMAKE_SOURCE_DIR}/isom_read.c
        ${CMAKE_SOURCE_DIR}/isom_store.c
        ${CMAKE_SOURCE_DIR}/box_funcs.c
        ${CMAKE_SOURCE_DIR}/box_code_base.c
        ${CMAKE_SOURCE_DIR}/box_dump.c
        ${CMAKE_SOURCE_DIR}/box_code_meta.c
        ${CMAKE_SOURCE_DIR}/avc_ext.c
        ${CMAKE_SOURCE_DIR}/box_code_drm.c
        ${CMAKE_SOURCE_DIR}/box_code_3gpp.c
        ${CMAKE_SOURCE_DIR}/box_code_apple.c
        ${CMAKE_SOURCE_DIR}/box_code_adobe.c
        ${CMAKE_SOURCE_DIR}/isom_intern.c
        ${CMAKE_SOURCE_DIR}/data_map.c
        ${CMAKE_SOURCE_DIR}/iff.c
        ${CMAKE_SOURCE_DIR}/meta.c
        ${CMAKE_SOURCE_DIR}/sample_descs.c
        ${CMAKE_SOURCE_DIR}/track.c
        ${CMAKE_SOURCE_DIR}/media.c
        ${CMAKE_SOURCE_DIR}/stbl_read.c
        ${CMAKE_SOURCE_DIR}/webvtt.c
)

SET(ISOBMFF_INC
        ${CMAKE_SOURCE_DIR}/include
)

add_filter(isobmff
        "${ISOBMFF_SRC}"
        ""
        []
        ""
        "${ISOBMFF_INC}"
        ""
        "1")