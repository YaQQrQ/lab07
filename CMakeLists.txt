cmake_minimum_required(VERSION 3.14)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/cpp-pm/hunter/archive/v0.23.314.tar.gz"
    SHA1 "572541b3a9e2c1ccb0c0e552f6dc12219c0d6a0b"
    LOCAL
)

project(print)
set(PRINT_VERSION_MAJOR 0)
set(PRINT_VERSION_MINOR 1)
set(PRINT_VERSION_PATCH 0)
set(PRINT_VERSION_TWEAK 0)
set(PRINT_VERSION
  ${PRINT_VERSION_MAJOR}.${PRINT_VERSION_MINOR}.${PRINT_VERSION_PATCH}.${PRINT_VERSION_TWEAK})
set(PRINT_VERSION_STRING "v${PRINT_VERSION}")

option(BUILD_TESTS "Build tests" OFF)

hunter_add_package(GTest)
find_package(GTest REQUIRED)

add_library(print STATIC src/print.cpp)
target_include_directories(print PUBLIC include)

if(BUILD_TESTS)
    enable_testing()
    add_executable(check tests/test.cpp)
    target_link_libraries(check print GTest::GTest GTest::Main)
    add_test(NAME check COMMAND check)
endif()

add_executable(demo demo/main.cpp)
target_link_libraries(demo print)
install(TARGETS demo RUNTIME DESTINATION bin)
