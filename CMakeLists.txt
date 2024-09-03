cmake_minimum_required(VERSION 3.8)
project(epuck_driver_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()


# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(action_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "srv/ChangeRobotState.srv"
  "action/SimpleMovement.action"
  "action/CollectSoundData.action"
  "action/CalibrateFormation.action"
  "msg/RecordActivation.msg"
  "msg/RecordResult.msg"
)


ament_export_dependencies(rosidl_default_runtime)


ament_package()
