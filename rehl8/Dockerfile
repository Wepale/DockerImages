FROM redhat/ubi8:8.5

ARG USER=yery
ARG PASS=yery

RUN yum -y update && yum -y install sudo
# Create yery user. -m create home dir; -G add secondary group
RUN adduser -m --shell /bin/bash yery && chpasswd <<<"$USER:$PASS" && echo "yery ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
USER yery
ENV PS1='\e[33;1m\u@\h: \e[31m\W\e[0m\$ '
WORKDIR /home/yery