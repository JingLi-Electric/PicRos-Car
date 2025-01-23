
## IMU
PicROS-Car使用轮趣科技的N100imu，可以通过在windows上用程序调节输出200HZ，400HZ。

使用说明：

https://blog.csdn.net/qq_32761549/article/details/126464807

代码：

https://github.com/sbgisen/fdilink_ahrs



## lidar

这里采用了 速腾16线 雷达，但是由于lio-sam仅支持velodyne，所以用[rs_to_velodyne](https://github.com/HViktorTsoi/rs_to_velodyne/)转化一下，不知道为啥，ros2 foxy无法正常编译，所以这里还是使用ros noetic。

由于lidar还承担避障的功能，所以把3d转成2d的雷达（rslidar_laserscan），并且对雷达进行裁剪（laser_filters-noetic-devel）。