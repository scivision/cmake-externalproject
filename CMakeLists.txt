cmake_minimum_required(VERSION 3.14)
project(DemoExt
LANGUAGES Fortran
VERSION 1.0.0
)

add_library(multiplier multiplier.f90)

target_include_directories(multiplier INTERFACE
$<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}/include>
$<INSTALL_INTERFACE:include>
)

set_target_properties(multiplier PROPERTIES
Fortran_MODULE_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/include
)

install(TARGETS multiplier)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/include/multiplier.mod
TYPE INCLUDE
)
