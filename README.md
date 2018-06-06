# OpenManipulator

[![GitHub version](https://badge.fury.io/gh/ROBOTIS-GIT%2Fopen_manipulator.svg)](https://badge.fury.io/gh/ROBOTIS-GIT%2Fopen_manipulator) [![Build Status](https://travis-ci.org/ROBOTIS-GIT/open_manipulator.svg?branch=master)](https://travis-ci.org/ROBOTIS-GIT/open_manipulator)

ROS-enabled OpenManipulator is a full open robot platform consisting of OpenSoftware​, OpenHardware and OpenCR (Embedded board).

# Documents
- http://emanual.robotis.com/docs/en/platform/openmanipulator/


# Set up
USB2Dynamixelを接続したら実行
※s USB2DynamixelのスイッチがRS485になっているか注意
`sudo chmod a+rw /dev/ttyUSB0`

# Demo Execute
Open Manipulatorの起動
`roslaunch open_manipulator_dynamixel_ctrl dynamixel_controller.launch`
Moveitの起動
`roslaunch open_manipulator_moveit open_manipulator_demo.launch`
Kinectの起動
`roslaunch kinect2_bridge kinect2_bridge.launch base_name:=camera fps_limit:=2`

## Kinect Position Parameters
`~/ros/src/open_manipulator/open_manipulator_description/urdf/open_manipulator_chain.xacro`

## 角度の上限下限について
上記の.xacroの中の joint->limit に, 速度/トルク/下限角/上限角, の順に記載されている.
これらを編集することでrviz上の軌道生成に制限を加えることができる.
