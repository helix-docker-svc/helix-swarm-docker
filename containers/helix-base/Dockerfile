# ========================================================================= #
# This docker files was built by the Perforce Software Swarm team to demo   #
# Swarm in a docker environment.                                            #
# ========================================================================= #

FROM ubuntu:focal
LABEL vendor="Perforce Software"
LABEL maintainer="Swarm Team (https://github.com/perforce/helix-swarm-docker)"
ARG P4REPO="deb http://package.perforce.com/apt/ubuntu focal release"

RUN \
  apt-get update && \
  DEBIAN_FRONTEND=noninteractive apt-get install -y wget curl unzip vim gnupg zip lsb-release

RUN \
  wget -qO - https://package.perforce.com/perforce.pubkey | apt-key add - && \
  echo "${P4REPO}\n" > /etc/apt/sources.list.d/perforce.list

RUN \
  apt-get update && \
  apt-get upgrade -y

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y -f helix-cli


CMD /bin/true
