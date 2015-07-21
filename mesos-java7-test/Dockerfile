FROM ubuntu:14.04.1
MAINTAINER Paul Otto <paul@ottoops.com>

RUN \
    echo "deb http://repos.mesosphere.io/ubuntu/ trusty main" > /etc/apt/sources.list.d/mesosphere.list && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF && \
    env DEBIAN_FRONTEND=noninteractive apt-get -y update && \
    apt-get -y install mesos=0.22.1-1.0.ubuntu1404 software-properties-common python-software-properties && \
    echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
    add-apt-repository -y ppa:webupd8team/java && \
    apt-get update && \
    apt-get install -y oracle-java7-installer && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /var/cache/oracle-jdk7-installer

# Ensure everything uses oraclejdk
RUN update-alternatives --set java /usr/lib/jvm/java-7-oracle/jre/bin/java

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-7-oracle
