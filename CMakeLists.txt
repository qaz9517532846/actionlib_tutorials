cmake_minimum_required(VERSION 3.0.2)
project(actionlib_tutorial)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  genmsg
  actionlib
  actionlib_msgs
  roscpp
  rospy
)

add_action_files(DIRECTORY action 
                 FILES 
                 DoDishes.action
                 Fibonacci.action
                 Averaging.action)

generate_messages(DEPENDENCIES actionlib_msgs std_msgs)

catkin_package(CATKIN_DEPENDS actionlib_msgs)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
  ${Boost_INCLUDE_DIRS}
)

#add_executable(do_dishes_server src/do_dishes_server.cpp)
#target_link_libraries(do_dishes_server ${catkin_LIBRARIES})

#add_executable(do_dishes_client src/do_dishes_client.cpp)
#target_link_libraries(do_dishes_client ${catkin_LIBRARIES})

#add_executable(fibonacci_server src/fibonacci_server.cpp)
#target_link_libraries(fibonacci_server ${catkin_LIBRARIES})
#add_dependencies(fibonacci_server ${actionlib_tutorial_EXPORTED_TARGETS})

#add_executable(fibonacci_client src/fibonacci_client.cpp)
#target_link_libraries(fibonacci_client ${catkin_LIBRARIES})
#add_dependencies(fibonacci_client ${actionlib_tutorial_EXPORTED_TARGETS})

#add_executable(averaging_server src/averaging_server.cpp)
#target_link_libraries(averaging_server ${catkin_LIBRARIES})
#add_dependencies(averaging_server ${actionlib_tutorial_EXPORTED_TARGETS})

#add_executable(averaging_client src/averaging_client.cpp)
#target_link_libraries(averaging_client ${catkin_LIBRARIES})
#add_dependencies(averaging_client ${actionlib_tutorial_EXPORTED_TARGETS})
