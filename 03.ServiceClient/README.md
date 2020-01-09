# Introduction

## Command

* Show service list
  - `ros2 service list`
  - Also show type: `ros2 service list -t`
* Service call
  - `ros2 service call <service_name> <service_type> <arguments>`

## C++

* Create package
```sh
ros2 pkg create --build-type ament_cmake cpp_service_client
```
* Add lifecycle_talker.cpp
* Add launch file
* Modify CMakeLists.txt: find_package, add_library, target_compile_definitions, ament_target_dependencies, rclcpp_components_register_node, install
* Build and run
```sh
colcon build --packages-select cpp_service_client
source install/local_setup.bash
ros2 run cpp_service_client add_two_ints_server
ros2 run cpp_service_client add_two_ints_client
```

## Python

* Create package
```sh
ros2 pkg create --build-type ament_python py_service_client
```
* Add add_two_ints_client.py, add_two_ints_server.py in `ros2_ws/src/py_service_client/py_service_client`
* Open package.xml: Modify description, license, version, and add exec_depend field.
* Open setup.py: Modify description, license, version, and add entry_point.
* Build and run
```sh
colcon build --packages-select py_pubsub
source install/setup.bash
ros2 run py_pubsub listener &
ros2 run py_pubsub talker
```

# Reference

* [Understanding ROS 2 services](https://index.ros.org/doc/ros2/Tutorials/Services/Understanding-ROS2-Services/)
* [C++ Demo Code](https://github.com/ros2/demos/tree/master/demo_nodes_cpp/src/services)
* [Python Demo Code](https://github.com/ros2/demos/tree/master/demo_nodes_py/demo_nodes_py/services)