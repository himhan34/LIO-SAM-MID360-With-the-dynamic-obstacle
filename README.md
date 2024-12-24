# LIO-SAM-MID360
This code is adapted for the Livox MID360 version of LIO-SAM.
It supports both six-axis and 9-axis IMU.

## Dependency

- It has the same dependencies as LIO-SAM.( [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM/) ）
- Please install the Livox ROS package to publish point cloud data(https://github.com/Livox-SDK/livox_ros_driver/) )

If using the Livox-ros-driver2 driver, you can switch to the branch[Livox-ros-driver2](https://github.com/nkymzsy/LIO-SAM-MID360/tree/Livox-ros-driver2) 。

## Prepare lidar data

For Livox MID360 LiDAR data, please use Livox's custom point cloud data format CustomMsg. 
That is, for the Livox ROS driver, please run 
livox_lidar_msg.launch.

## Run
To use the built-in 6-axis IMU, please run the corresponding configuration.

```
roslaunch lio_sam run6axis.launch
```

To use the 9-axis IMU, please run the appropriate configuration.
```
roslaunch lio_sam run9axis.launch
```

## Test

- Indoor environment rotation test.
<img src="doc/indoorTest.gif" alt="indoorTest.gif" title="Indoor Test" style="zoom: 100%;"/>

- Outdoor environment tilt handheld test.
<img src="doc/Outdoor.gif" alt="Outdoor.gif" title="Outdoor" style="zoom: 100%;"/>

- Indoor environment.
<img src="doc/indoor.gif" alt="indoor.gif" title="indoor" style="zoom: 100%;"/>

## Note
- Ensure the timestamps of the LiDAR and IMU are synchronized.
- When using an external IMU, remember to adjust the extrinsic parameters between the LiDAR and IMU in the param.yaml file.
- The default six-axis IMU uses the built-in IMU of the MID360. The acceleration unit is g, so it should be multiplied by the gravitational acceleration to convert it to m/s^2 during processing. If another six-axis IMU is used, comment out this line.
- If you observe IMU odometry jitter, adjust the IMU parameters accordingly.


## TODO

- [ ] Feature extraction and optimization.
## Acknowledgement

- [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM/)
- [LIO-SAM-DetailedNote](https://github.com/smilefacehh/LIO-SAM-DetailedNote)
- [LIO_SAM_6AXIS](https://github.com/JokerJohn/LIO_SAM_6AXIS)
