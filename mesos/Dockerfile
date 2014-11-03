FROM ubuntu:14.04
MAINTAINER Paul Otto <paul@ottoops.com>

RUN \
    echo "deb http://repos.mesosphere.io/ubuntu/ trusty main" > /etc/apt/sources.list.d/mesosphere.list && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF && \
    env DEBIAN_FRONTEND=noninteractive apt-get -y update && \
    apt-get -y install mesos=0.20.1-1.0.ubuntu1404
