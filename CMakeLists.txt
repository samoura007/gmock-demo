cmake_minimum_required(VERSION 3.10)
project(RegistrationMockDemo)

set(CMAKE_CXX_STANDARD 11)

find_package(GTest REQUIRED)

add_executable(runRegistrationTests 
    registration_service_test.cpp 
    registration_service.cpp
)

target_link_libraries(runRegistrationTests 
    GTest::gmock 
    GTest::gtest
    GTest::gtest_main 
    pthread
)

enable_testing()
add_test(NAME RegistrationTests COMMAND runRegistrationTests)
