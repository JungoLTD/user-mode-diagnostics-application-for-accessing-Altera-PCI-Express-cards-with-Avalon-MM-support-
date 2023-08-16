cmake_minimum_required(VERSION 3.0)

project(avalonmm_diag C)
include(../../../../include/wd.cmake)
include_directories(
    ../../shared
    ../../../../include
    )

set (SRCS
    avalonmm_diag.c
    avalonmm_lib.c
    avalonmm_lib.h
    avalonmm_internal.h)

add_executable(avalonmm_diag ${SRCS} ${SAMPLE_SHARED_SRCS})
target_link_libraries(avalonmm_diag ${WDAPI_LIB})
set_target_properties(avalonmm_diag PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${ARCH}/")
add_compile_definitions(HAS_INTS)

# This sample can be compiled for designs running on
# different kinds of target hardware.
#
# To run on the Stratix 10 GX L-Tile development kit,
# enable the Stratix10 define. For the default design,
# comment it out.

# add_definitions(-DSTRATIX10=1)

# You can specify the Vendor ID and Device ID of your
# design via the following defines.

# add_definitions(-DAVALONMM_DEFAULT_VENDOR_ID=0x8086)
# add_definitions(-DAVALONMM_DEFAULT_DEVICE_ID=0x1234)

