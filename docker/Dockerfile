FROM osrf/ros:foxy-desktop
LABEL maintainer="kheo1772@gmail.com"

ENV WORKSPACE_DIR="/workspace"
ENV WORKSPACE_SOURCE_DIR="/workspace/src"
RUN mkdir -p ${WORKSPACE_SOURCE_DIR} 
WORKDIR ${WORKSPACE_DIR}

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update -y
RUN apt-get install -y --no-install-recommends git cmake g++ libfltk1.1-dev libjpeg8-dev libpng-dev libglu1-mesa-dev libltdl-dev	

RUN cd ${WORKSPACE_SOURCE_DIR} && git clone https://github.com/rtv/Stage.git
RUN cd ${WORKSPACE_SOURCE_DIR} && git clone https://github.com/harderthan/stage_ros2.git

SHELL ["/bin/bash", "-c", "source /opt/ros/foxy/setup.bash"]
RUN cd ${WORKSPACE_DIR} && colcon build --symlink-install --cmake-args -DOpenGL_GL_PREFERENCE=LEGACY