include(FetchContent)

# Remove unnecessary build files
# and steps from GTest's CMake
option(BUILD_GMOCK OFF)
option(INSTALL_GTEST OFF)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        v1.15.2
)
FetchContent_MakeAvailable(googletest)
add_library(GTest::GTest INTERFACE IMPORTED)
target_link_libraries(GTest::GTest INTERFACE gtest_main)

add_executable(multiply_test multiply_test.cpp)

target_link_libraries(multiply_test
 PRIVATE
  GTest::GTest
  multiply)

add_test(multiply_gtests multiply_test)
