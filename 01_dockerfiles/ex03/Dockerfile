
FROM ubuntu

RUN apt update 
&& apt upgrade -y

RUN apt install curl openssh-server \
ca-certificates postfix -y

RUN curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash \
apt install gitlab-ce -y