这里是启动小车节点的命令
默认路径在 ws
## lio-sam建图
单独启动好像有点问题
roslaunch nav_pkg lio_map.launch
ssh zen@192.168.8.103
### 小车底盘

```bash
sudo ip link set can0 type can bitrate 500000
yunyibot

sudo ip link set can0 up
roslaunch yhs_can_control yhs_can_control.launch  
```

### lidar
1.
roslaunch rslidar_sdk start.launch 
2.
roslaunch rslidar_laserscan rslidar_laserscan.launch 
3.
roslaunch laser_filters box_filter_example.launch 


### imu 
roslaunch fdilink_ahrs ahrs_data.launch 

### robot_destription
roslaunch nav_pkg steering_yhs_robot.launch


###  录制rosbag
```bash
cd rosbag

r
```



### 开始建图

```

roslaunch lio_sam run.launch
rosbag play xx.bag --clock --topics /imu /velodyne_points
```


## 导航

### 定位ndt

roslaunch nav_pkg steering_yhs_nav_ndt.launch

roslaunch nav_pkg steering move_base.launch



## 地图保存

在 downloads中
修改位置
roslaunch pcd2pgm run.launch 

rosrun map_server map_saver 


