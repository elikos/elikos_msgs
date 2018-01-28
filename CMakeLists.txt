cmake_minimum_required(VERSION 2.8.3)
project(elikos_msgs)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

# Disable unused message generation languages
set(ENV{ROS_LANG_DISABLE} genlisp:gennodejs:geneus)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
	std_msgs
	geometry_msgs
	trajectory_msgs
	actionlib_msgs
	sensor_msgs
	message_generation
	actionlib
)

################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
add_message_files(
	FILES
	AICmd.msg
	BoundingBox.msg
	BoundingBoxArray.msg
	CalibDetection.msg
	CalibPreprocessing.msg
	ColorDetectionInfo.msg
	ColorHSV.msg
	ColorHSVRange.msg
	Intersection.msg
	IntersectionArray.msg
	Matrix3.msg
	PositionAndProbability.msg
	PositionAndProbabilityArray.msg
	RobotPos.msg
	RobotPosArray.msg
	RobotRaw.msg
	RobotRawArray.msg
	StampedMatrix3.msg
	TargetRobot.msg
	TargetRobotArray.msg
	TrajectoryCmd.msg
)

## Generate services in the 'srv' folder
add_service_files(
	FILES
	FileManipulation.srv
	GetConfigFiles.srv
	SelectCameraFeedWithIndex.srv
	SelectCameraFeedWithFrameID.srv
)

# Generate actions in the 'action' folder
add_action_files(
  FILES
  CheckForObjects.action
)

## Generate added messages and services with any dependencies listed here
generate_messages( DEPENDENCIES
	std_msgs
	geometry_msgs
	trajectory_msgs
	actionlib_msgs
	sensor_msgs
)

###################################
## catkin specific configuration ##
###################################

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES elikos_msgs
#  CATKIN_DEPENDS 
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
	include
	${catkin_INCLUDE_DIRS}
)