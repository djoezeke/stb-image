cmake_minimum_required(VERSION 3.16...4.1.1 FATAL_ERROR)

#--------------------------------------------------------------------
# Project and version.
#--------------------------------------------------------------------

project(Stb-Image)

if (CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
  set(STBIMAGE_IS_TOP_LEVEL ON)
else()
  set(STBIMAGE_IS_TOP_LEVEL OFF)
endif()

#--------------------------------------------------------------------
# Configure variables for the library   
#--------------------------------------------------------------------

set(STBIMAGE_LIB_NAME "stbimage")

set(STBIMAGE_TARGET_NAME  ${STBIMAGE_LIB_NAME})
set(STBIMAGE_SOURCE_FILE "src/stb_image.c")
set(STBIMAGE_INCLUDE_FILE "include/stb_image.h")

#--------------------------------------------------------------------
# Build library
#--------------------------------------------------------------------

add_library(${STBIMAGE_LIB_NAME})
target_sources(${STBIMAGE_LIB_NAME} PRIVATE ${STBIMAGE_SOURCE_FILE})
target_include_directories(${STBIMAGE_TARGET_NAME} PUBLIC
 $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>)
