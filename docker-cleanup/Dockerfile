FROM ubuntu:14.04
MAINTAINER Paul Otto <paul@ottoops.com>

RUN \
  env DEBIAN_FRONTEND=noninteractive apt-get update -qqy && apt-get install -qqy \
    apt-transport-https \
    ca-certificates \
    lxc \
    iptables

# Install Docker from Docker Inc. repositories.
RUN \
    echo deb https://get.docker.io/ubuntu docker main > /etc/apt/sources.list.d/docker.list && \
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 36A1D7869245C8950F966E92D8576A8BA88D21E9 && \
    apt-get update -qq && \
    apt-get install -qqy lxc-docker

ADD docker-cleanup.sh /docker-cleanup.sh

VOLUME /var/lib/docker

CMD ["/docker-cleanup.sh"]