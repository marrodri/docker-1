
FROM ubuntu:latest

RUN apt update \
&& apt upgrade -y

RUN apt install curl openssh-server \
ca-certificates postfix -y

RUN curl -fsSL https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt install gitlab-ce -y


# CONTINUE HERE
# RUN perl -pi.bak -e 's/http/https/g' /etc/gitlab/gitlab.rb
# RUN perl -pi.bak -e 's/gitlab.example.com/git.marrodri-labs.pw/g' /etc/gitlab/gitlab.rb

# next steps
#RUN apt install letsencrypt -y && letsencrypt certonly --standalone\
#  --agree-tos --no-eff-email --agree-tos --email laza.mar64@gmail.com -d git.marrodri-labs.pw

# RUN mkdir -p /etc/gitlab/ssl && openssl dhparam -out /etc/gitlab/ssl/dhparams.pem 2048 && chmod 600 /etc/gitlab/ssl/*


# 'http://gitlab.example.com'