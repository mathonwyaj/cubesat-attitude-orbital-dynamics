cmake_minimum_required(VERSION 3.10)

project(CubeSatAttitudeController C)

add_executable(test_controller
    test_controller.c
    attitude_controller.c
)

target_link_libraries(test_controller m)
