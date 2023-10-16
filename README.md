# slam_benchmark
Easy LIDAR-based bringup for mostly all ROS SLAM packages

## SLAM packages in use - slam_package_name:
* `gmapping`
* `hector_slam`

## How to use?
To try specific SLAM with your bag file and LIDAR scheme you should do this steps:
```
1. [in test_slam.launch] change configuration to match your lidar scheme.
2. [in catkin ws] mkdir bag_files
3. mv "your_bag_file".bag bag_files
4. roslaunch slam_benchmark test_slam.launch SLAM_type:="hector_slam" bag_file:="your_bag_file"
```
To try specific SLAM with your bag file and our LIDAR scheme you should do this steps:
```
1. repeate 2-3 steps above
2. roslaunch slam_benchmark test_slam.launch SLAM_type:="slam_package_name" bag_file:="your_bag_file" scanner1:="/your_cloud_topic" scanner2:="/your_other_cloud_topic"
```
