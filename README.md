# Atlas MuJoCo ROS2

<div align="center">
    <img src="./atlas_sim.png">
</div>

## Introduction

This package is developed with [ROS2](https://docs.ros.org/en/humble/index.html) based on [ihmc_atlas_ros](https://github.com/ihmcrobotics/ihmc_atlas_ros).

The files include:

1. The XML file `(description/model/xml/atlas/atlas_v5.xml)` of Atlas V5 for the simulation in [MuJoCo](https://mujoco.org/).
2. A class named `MuJoCoMessageHandler` is also provided, which publishes the robot joint state and imu message. The `odom` message is just the real pose of the robot in simulation. More details can be found in the cpp file `src/simulation/mujoco/src/MuJoCoMessageHandler.cpp`.
3. ROS2 ([version](https://docs.ros.org/en/humble/index.html)) is needed to run this package.

## Installation

```
# Create your own workspace
cd ~/ & mkdir -p your_workspace/src
```

```
# Clone this package to your_workspace/src
cd ~/your_workspace/src & git clone https://github.com/MindSpaceInc/Atlas-MuJoCo-ROS2.git
```

```
# Build (DO NOT remove `--symlink-install`)
colcon build --symlink-install 
```

```
# Setup env
source ../install/setup.bash
```

```
# Run simulation 
ros2 launch mujoco simulation_launch.py
```

Now your can open a new terminal and use command `ros2 topic list` to see the below topics
```
/parameter_events
/rosout
/simulation/actuators_cmds
/simulation/imu_data
/simulation/joint_states
/simulation/odom  # the pose and twist of robot in simulation 
/simulation/touch_sensor  # force on foot
```

