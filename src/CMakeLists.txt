# -------------------------------------------------------------
# file: CMakeLists.txt
# -------------------------------------------------------------
# -------------------------------------------------------------
# Created November 18, 2022 by Perkins
# Last Change: 2022-11-18 09:05:36 d3g096
# -------------------------------------------------------------

add_library(ANN
  ANN.cpp brute.cpp kd_tree.cpp kd_util.cpp kd_split.cpp 
  kd_dump.cpp kd_search.cpp kd_pr_search.cpp kd_fix_rad_search.cpp 
  bd_tree.cpp bd_search.cpp bd_pr_search.cpp bd_fix_rad_search.cpp 
  perf.cpp)

# -------------------------------------------------------------
# Installation
# -------------------------------------------------------------
install(TARGETS ANN
  DESTINATION lib
)
  
