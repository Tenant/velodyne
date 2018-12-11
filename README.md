[![Build Status](https://travis-ci.org/ros-drivers/velodyne.svg?branch=master)](https://travis-ci.org/ros-drivers/velodyne)

Overview
========

Velodyne<sup>1</sup> is a collection of ROS<sup>2</sup> packages supporting `Velodyne high
definition 3D LIDARs`<sup>3</sup>.

**Warning**:

  The master branch normally contains code being tested for the next
  ROS release.  It will not always work with every previous release.
  To check out the source for the most recent release, check out the
  tag `velodyne-<version>` with the highest version number.

The current ``master`` branch works with ROS Indigo and Kinetic.
CI builds are currently run for Lunar and Melodic but extensive
testing has not been completed in those environments.

- <sup>1</sup>ROS: http://www.ros.org
- <sup>2</sup>Velodyne: http://www.ros.org/wiki/velodyne
- <sup>3</sup>`Velodyne high definition 3D LIDARs`: http://www.velodynelidar.com/lidar/lidar.aspx



# Tutorial

**Convert Raw Velodyne VLP16 pcap to bagFile**

Once you have built that driver in your catkin workspace, run these commands in separate terminal windows:

```bash
roscore
```

```bash
rosrun velodyne_driver velodyne_node _model:=VLP16 _pcap:=/your/pcap/path/data.pcap _read_once:=true
```

```bash
rosrun rosbag record -O your_vlp16_070815.bag /velodyne_packets
```



**Combine pcap and GPS into rosbag**

