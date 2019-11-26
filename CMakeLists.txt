cmake_minimum_required(VERSION 3.0)
project(DemoExt LANGUAGES C)

add_library(times_two times_two.c)

set_target_properties(times_two PROPERTIES
#  Fortran_MODULE_DIRECTORY ${CMAKE_BINARY_DIR}
  ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}
  LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

# normally we'd not do tests, etc. by if() return() endif() but here we do an error to show
if(CMAKE_PROJECT_DIR STREQUAL PROJECT_SOURCE_DIR)
  message(FATAL_ERROR "not using as externalProject")
endif()