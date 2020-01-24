cmake_minimum_required(VERSION 3.14)
project(DemoExt LANGUAGES Fortran)

add_library(timestwo times_two.f90)
target_include_directories(timestwo INTERFACE ${CMAKE_CURRENT_BINARY_DIR}/include)
set_target_properties(timestwo PROPERTIES
  Fortran_MODULE_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/include)
