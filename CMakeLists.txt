cmake_minimum_required(VERSION 3.15...3.27)

project(unitree_interface)
SET(CMAKE_CXX_STANDARD 17)

add_library(unitree_interface INTERFACE)

target_include_directories(unitree_interface
    INTERFACE 
    include
    thirdparty/include
    thirdparty/include/ddscxx
    )

target_link_libraries(unitree_interface
    INTERFACE 
    ${CMAKE_CURRENT_SOURCE_DIR}/lib/${CMAKE_SYSTEM_PROCESSOR}/libunitree_sdk2.a
    ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/lib/${CMAKE_SYSTEM_PROCESSOR}/libddsc.so
    ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/lib/${CMAKE_SYSTEM_PROCESSOR}/libddscxx.so)

link_libraries(unitree_interface)

add_executable(test_publisher example/helloworld/publisher.cpp example/helloworld/HelloWorldData.cpp)
add_executable(test_subscriber example/helloworld/subscriber.cpp example/helloworld/HelloWorldData.cpp)
add_executable(high_follow_sin example/high_level/follow_sin.cpp)
add_executable(sportmode_test example/high_level/sportmode_test.cpp)
add_executable(low_level example/low_level/low_level.cpp)
add_executable(stand_example_go2 example/low_level/stand_example_go2.cpp)
add_executable(stand_example_b2  example/low_level/stand_example_b2.cpp)
add_executable(wireless example/wireless/wireless.cpp)
add_executable(advanced_gamepad example/advanced_gamepad/main.cpp)
add_executable(state_machine_example example/state_machine/main.cpp)
add_executable(test_jsonize example/jsonize/test_jsonize.cpp)
add_executable(robot_state_client_example example/client/robot_state_client_example.cpp)
add_executable(sport_client_example example/client/sport_client_example.cpp)
add_executable(video_client_example example/client/video_client_example.cpp)
add_executable(vui_client_example example/client/vui_client_example.cpp)
add_executable(h1_arm_sdk_dds_example example/humanoid/high_level/h1_arm_sdk_dds_example.cpp)
add_executable(h1_loco_example_client example/humanoid/high_level/h1_loco_example_client.cpp)
add_executable(h1_low_level_example example/humanoid/low_level/humanoid.cpp)
