# -------------------------------------------------------------
# file: CMakeLists.txt
# -------------------------------------------------------------
# -------------------------------------------------------------
# Created November 18, 2022 by Perkins
# Last Change: 2022-11-18 08:25:34 d3g096
# -------------------------------------------------------------

cmake_minimum_required (VERSION 3.16)

project(ANN)

enable_language(CXX)

# -------------------------------------------------------------
# options
# -------------------------------------------------------------
option(ANN_PERF "Enable performance evaluation." OFF)

# -------------------------------------------------------------
# Investigate environment
# -------------------------------------------------------------
CHECK_INCLUDE_FILE_CXX(limits.h HAVE_LIMITS_H)
CHECK_INCLUDE_FILE_CXX(float.h HAVE_FLOAT_H)

if (NOT (HAVE_LIMITS_H OR HAVE_FLOAT_H))
  add_definitions("-DANN_NO_LIMITS_H")
endif()

check_function_exists(random HAVE_RANDOM)
if (NOT HAVE_RANDOM)
  add_definitions("-DANN_NO_RANDOM")
endif()

# -------------------------------------------------------------
# Subdirectories
# -------------------------------------------------------------
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_subdirectory(src)


# -------------------------------------------------------------
# Installation
# -------------------------------------------------------------
