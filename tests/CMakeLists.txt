add_executable(TestIO TestIO.cpp)
target_link_libraries(TestIO
  PRIVATE GTest::gtest_main ${MAIN_LIB} nlohmann_json::nlohmann_json)
target_include_directories(TestIO PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../src)

add_executable(TestMatching TestMatching.cpp)
target_link_libraries(TestMatching
  PRIVATE GTest::gtest_main ${MAIN_LIB})
target_include_directories(TestMatching PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../src)

include(GoogleTest)
gtest_discover_tests(TestIO)
gtest_discover_tests(TestMatching)
