# This is an auto generated Dockerfile for ros:ros1-bridge
# generated from docker_images_ros2/ros1_bridge/create_ros_ros1_bridge_image.Dockerfile.em
FROM ros:eloquent-ros-base-bionic

# setup keys
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

# setup sources.list
RUN echo "deb http://packages.ros.org/ros/ubuntu bionic main" > /etc/apt/sources.list.d/ros1-latest.list

ENV ROS1_DISTRO melodic
ENV ROS2_DISTRO eloquent

# label ros packages
LABEL org.osrfoundation.ros-melodic-ros-comm.sha256=41f220c83c352d5a3cecaad37614920c8a7c338480e4083699d7f1d1eae06fc4 \
      org.osrfoundation.ros-melodic-roscpp-tutorials.sha256=f49fca05c2692ea5c58107c155fb708a7c40b76ff6e90c3fc223c4c0e47fd083 \
      org.osrfoundation.ros-melodic-rospy-tutorials.sha256=b990f747b59195d9bd749581737f1fb0bd289e8e1389e32d26024bc6101d7922

# install ros packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-melodic-ros-comm=1.14.9-1* \
    ros-melodic-roscpp-tutorials=0.9.3-1* \
    ros-melodic-rospy-tutorials=0.9.3-1* \
    && rm -rf /var/lib/apt/lists/*

# label ros2 packages
LABEL org.osrfoundation.ros-eloquent-ros1-bridge.sha256=678988e1c257e8433f426db2c28e65c189f85eac82fdb4084101d3d0124c4e0e \
      org.osrfoundation.ros-eloquent-demo-nodes-cpp.sha256=e07fd5f0b1afbd1695b5afb0a8e6d8bcba213ff1690fe5c8768a364578d0fcfc \
      org.osrfoundation.ros-eloquent-demo-nodes-py.sha256=36cc41b867918c9a2206ec8d1a1643529523fce4d876736e85c285e6fd9f2d5f

# install ros2 packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-eloquent-ros1-bridge=0.8.2-3* \
    ros-eloquent-demo-nodes-cpp=0.8.4-1* \
    ros-eloquent-demo-nodes-py=0.8.4-1* \
    && rm -rf /var/lib/apt/lists/*

# install downstream packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    python-rosdep \
    && rm -rf /var/lib/apt/lists/*

# setup entrypoint
COPY ./ros_entrypoint.sh /

