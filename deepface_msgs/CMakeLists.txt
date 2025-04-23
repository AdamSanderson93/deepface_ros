cmake_minimum_required(VERSION 3.0.2)
project(deepface_msgs)

find_package(catkin REQUIRED COMPONENTS
    roscpp
    rospy
    std_msgs
    message_generation
    sensor_msgs
)

add_message_files(
    FILES
    Emotion.msg
    Race.msg
    Gender.msg
    FaceDetection.msg
    FaceAnalysis.msg
    FacesAnalysis.msg
)

add_service_files(
    FILES
    FaceVerification.srv
    FaceRecognition.srv
    FacesAnalysisSrv.srv
    ImageFacesAnalysis.srv
)

generate_messages(
    DEPENDENCIES
        std_msgs
        sensor_msgs
)

catkin_package(
    CATKIN_DEPENDS roscpp rospy std_msgs sensor_msgs message_runtime
)

include_directories(
    ${catkin_INCLUDE_DIRS}
)
