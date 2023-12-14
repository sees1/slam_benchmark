# slam_benchmark
Easy LIDAR-based bringup for mostly ROS SLAM and localization packages

  ## SLAM packages in use - SLAM_type:
* `gmapping`
* `hector_slam`
* `rtabmap`
* `rtabmap_broken`
* `octomap_mapping`

## Localization packages in use - localization_type:
* `amcl`
* `als`
* `gmcl`

## How to use?
### SLAM usage:
To try specific SLAM with your bag file and LIDAR scheme you should do this steps:
```
1. [in test_slam.launch] change configuration to match your lidar scheme.
2. [in slam_benchmark dir] mkdir bag_files
3. mv "your_bag_file".bag /path/to/your/bag/folder/bag_files
4. roslaunch slam_benchmark test_slam.launch SLAM_type:="hector_slam" bag_file:="your_bag_file" scanner1:="/points2_front" scanner2:="/points2_rear" inter_rviz:="true" rviz_config:="basic"
```
To try specific SLAM with your bag file and our LIDAR scheme you should do this steps:
```
1. repeate 2-3 steps above
2. roslaunch slam_benchmark test_slam.launch SLAM_type:="slam_package_name" bag_file:="your_bag_file" scanner1:="/your_cloud_topic" scanner2:="/your_other_cloud_topic"
```
### Localization usage:
To try specific Localization package with your bag file and LIDAR scheme you should do this steps:
```
1. [in localization_test.launch] change configuration to match your lidar scheme.
2. [in slam_benchmark dir] mkdir bag_files
3. mv "your_bag_file".bag /path/to/your/bag/folder/bag_files
4. roslaunch slam_benchmark localization_type.launch localization_type:="amcl" bag_file:="your_bag_file" scanner1:="/points2_front" scanner2:="/points2_rear" inter_rviz:="true" rviz_config:="turtlebot3_navigation"
```
To try specific Localization package with your bag file and our LIDAR scheme you should do this steps:
```
1. repeate 2-3 steps above
2. roslaunch slam_benchmark localization_type.launch localization_type:="amcl" bag_file:="your_bag_file" scanner1:="/points2_front" scanner2:="/points2_rear" inter_rviz:="true" rviz_config:="turtlebot3_navigation"
```
## Arguments
### slam_test.launch
```
* SLAM_type - type of SLAM algorithm
```
### localization_test.launch
```
* localization_type - type of Localization algorithm
```
### common arguments
```
* bag_file - bag file for rosbag usage
* map_file - map file for map server usage
* scanner1 - name of first topic, which publish PointCloud2
* scanner2 - name of second topic, which publish PointCloud2
* inter_rviz - param controll rviz behaviour, true - rviz will launch in this package, false - if not
* rviz_config - name of rviz config file
```
