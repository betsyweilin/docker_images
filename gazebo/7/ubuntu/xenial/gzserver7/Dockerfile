# This is an auto generated Dockerfile for gazebo:gzserver7
# generated from docker_images/create_gzserver_image.Dockerfile.em
FROM ubuntu:xenial

# install packages
RUN apt-get update && apt-get install -q -y --no-install-recommends \
    dirmngr \
    gnupg2 \
    lsb-release \
    && rm -rf /var/lib/apt/lists/*

# setup keys
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D2486D2DD83DB69272AFE98867170598AF249743

# setup sources.list
RUN . /etc/os-release \
    && echo "deb http://packages.osrfoundation.org/gazebo/$ID-stable `lsb_release -sc` main" > /etc/apt/sources.list.d/gazebo-latest.list

# label gazebo packages
LABEL org.osrfoundation.gazebo7.sha256=b1aee9ca46363b8b8ae56503af3876466ced9d86b166b69af633204e74317024

# install gazebo packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    gazebo7=7.16.1-1* \
    && rm -rf /var/lib/apt/lists/*

# setup environment
EXPOSE 11345

# setup entrypoint
COPY ./gzserver_entrypoint.sh /

ENTRYPOINT ["/gzserver_entrypoint.sh"]
CMD ["gzserver"]
