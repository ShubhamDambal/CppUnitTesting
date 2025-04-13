cmake_minimum_required(VERSION 3.10)
project(CppUnitTesting)

set(CMAKE_CXX_STANDARD 11)

# GoogleTest setup
add_subdirectory(extern/googletest)

# Source files
include_directories(include)
add_executable(my_project src/main.cpp)

# Unit testing
enable_testing()
add_executable(test_myfunctions test/test_myfunctions.cpp)
target_link_libraries(test_myfunctions gtest gtest_main)
add_test(NAME MyTest COMMAND test_myfunctions)
