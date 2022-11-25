#
# CMakeLists.txt for tinyfiledialogs. Provides a static/shared library target for
# cmake projects. The library target is also installable.
#

cmake_minimum_required(VERSION 3.0.0)

project(tinyfiledialogs VERSION "3.9.0" LANGUAGES C)

# Build a static library by default
#
option(BUILD_SHARED_LIBS OFF)
option(MORE_DIALOGS OFF)

add_library(tinyfiledialogs STATIC "src/tinyfiledialogs.c")
target_include_directories(tinyfiledialogs PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include")

if (MORE_DIALOGS)
	target_sources(tinyfiledialogs PUBLIC "src/tinyfd_moredialogs.c")
endif ()
