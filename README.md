# LIO-SAM-MID360

This code is the LIO-SAM version adapted for Livox MID360. Supports the use of six-axis and nine-axis IMUs \
[本代码为LIO-SAM适配Livox MID360版本。
支持使用六轴和九轴IMU]

## Dependency

Same dependencies as LIO-SAM ( LIO-SAM )
Please install the LIVOX ROS package to publish point cloud data ( Livox ROS driver )
If you use the Livox-ros-driver2 driver, you can switch the branch to Livox-ros-driver2 \

[- 与LIO-SAM有相同依赖 ( [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM/) ）
- 请安装LIVOX ROS包用于发布点云数据 ( [览沃 ROS 驱动程序](https://github.com/Livox-SDK/livox_ros_driver/) )

如果使用Livox-ros-driver2 驱动可以切换分支为 [Livox-ros-driver2](https://github.com/nkymzsy/LIO-SAM-MID360/tree/Livox-ros-driver2)]

## Prepare lidar data

For Livox MID360 data, please use Livox's custom point cloud data CustomMsg, that is, run livox_lidar_msg.launch for the LIVOX ROS driver. \
[Livox MID360雷达数据请使用览沃自定义点云数据`CustomMsg`，即LIVOX ROS驱动请运行`livox_lidar_msg.launch`]

## Run

If you use the built-in 6-axis IMU, please run \
[使用自带的6轴IMU请运行]

```
roslaunch lio_sam run6axis.launch
```

If you use the 9-axis IMU, please run \
[使用9轴IMU请运行]

```
roslaunch lio_sam run9axis.launch
```

## Test
Indoor environment rotation test \
[- 室内环境旋转测试]
<img src="doc/indoorTest.gif" alt="indoorTest.gif" title="Indoor Test" style="zoom: 100%;"/>

Outdoor environment tilt handheld \
[- 室外环境 倾斜手持]
<img src="doc/Outdoor.gif" alt="Outdoor.gif" title="Outdoor" style="zoom: 100%;"/>

Indoor environment \
[- 室内环境]
<img src="doc/indoor.gif" alt="indoor.gif" title="indoor" style="zoom: 100%;"/>

## Note
Pay attention to aligning the timestamps of Lidar and IMU. \
[- 注意对齐Lidar与IMU的时间戳。]

If you use a non-built-in IMU, pay attention to modifying the external parameters of LiDAR and IMU. (param.yaml file) \
[- 使用非自带IMU注意修改Lidai与IMU的外参。(param.yaml文件)]

When processing, multiply the gravity acceleration to convert to m/s^2. If you use other six-axis IMUs, you need to comment this statement. \
[- 六轴IMU默认使用MID360内置的IMU，加速度单位为g，处理时乘重力加速度转换为m/s^2，如果使用其他六轴IMU需要注释这条语句。]

If you observe the IMU odometer jitter, please adjust the IMU parameters \
[- 如果观察到IMU里程计抖动的话，请调节IMU参数]

## TODO
Extract feature optimization \
- [提取特征优化]

## Acknowledgement

- [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM/)
- [LIO-SAM-DetailedNote](https://github.com/smilefacehh/LIO-SAM-DetailedNote)
- [LIO_SAM_6AXIS](https://github.com/JokerJohn/LIO_SAM_6AXIS)
