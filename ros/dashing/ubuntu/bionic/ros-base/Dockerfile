# This is an auto generated Dockerfile for ros:ros-base
# generated from docker_images_ros2/create_ros_image.Dockerfile.em
FROM ros:dashing-ros-core-bionic

# install bootstrap tools
RUN apt-get update && apt-get install --no-install-recommends -y \
    build-essential \
    git \
    python3-colcon-common-extensions \
    python3-colcon-mixin \
    python3-rosdep \
    python3-vcstool \
    && rm -rf /var/lib/apt/lists/*

# bootstrap rosdep
RUN rosdep init && \
  rosdep update --rosdistro $ROS_DISTRO

# setup colcon mixin and metadata
RUN colcon mixin add default \
      https://raw.githubusercontent.com/colcon/colcon-mixin-repository/master/index.yaml && \
    colcon mixin update && \
    colcon metadata add default \
      https://raw.githubusercontent.com/colcon/colcon-metadata-repository/master/index.yaml && \
    colcon metadata update

# label ros2 packages
LABEL org.osrfoundation.ros-dashing-ros-base.sha256=12179b6ee23dffe54e835b26afa82d7a1099918d7924bad14e10934f9ee81d62

# install ros2 packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-dashing-ros-base=0.7.4-1* \
    && rm -rf /var/lib/apt/lists/*

