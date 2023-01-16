cmake_minimum_required(VERSION 3.12)

set(This Example)

project(${This} C CXX)

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

enable_testing()

add_subdirectory(googletest)

set(
    Sources 
    main.cpp
)



add_executable(
    ${This}
    ${Sources}
)

target_link_libraries(${This} PUBLIC
    gtest_main
)

add_test(
    Name ${This}
    COMMAND ${This}
)
