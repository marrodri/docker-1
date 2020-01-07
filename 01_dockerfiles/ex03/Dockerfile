
FROM ubuntu:latest

RUN apt update \
&& apt upgrade -y

RUN apt install curl openssh-server \
ca-certificates postfix -y

RUN curl -fsSL https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
# RUN apt install gitlab-ce -y