cmake_minimum_required(VERSION 3.5)

project(test LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# core
include_directories("../core")

# googletest
set(GTEST_CLONED "googletest")
include_directories(${GTEST_CLONED}/googletest)
include_directories(${GTEST_CLONED}/googletest/include)

add_executable(test
    main.cpp
    test_julian.cpp
    "${GTEST_CLONED}/googletest/src/gtest-all.cc"
)

target_link_libraries(test core)
