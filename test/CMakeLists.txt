# -------------------------------------------------------------
# file: CMakeLists.txt
# -------------------------------------------------------------
# -------------------------------------------------------------
# Created November 18, 2022 by Perkins
# Last Change: 2022-11-18 09:21:40 d3g096
# -------------------------------------------------------------

# -------------------------------------------------------------
# programs
# -------------------------------------------------------------
add_executable(ann_test ann_test.cpp rand.cpp)
target_link_libraries(ann_test ANN)

# -------------------------------------------------------------
# Installation
# -------------------------------------------------------------
install(TARGETS 
  ann_test
  DESTINATION bin
)

install(FILES
  test1-data.pts
  test1.in
  test1-query.pts
  test1.save
  test2-data.pts
  test2.in
  test2-query.pts
  test2.save
  DESTINATION share/ANN/test
)
