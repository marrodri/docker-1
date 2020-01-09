
FROM ubuntu:latest

RUN apt update \
&& apt upgrade -y

RUN apt install curl openssh-server \
ca-certificates postfix vim ufw -y

RUN curl -fsSL https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt install gitlab-ce -y


# CONTINUE HERE
RUN perl -pi.bak -e 's/http:\/\/gitlab.example.com/https:\/\/git.marrodri-labs.pw/g' /etc/gitlab/gitlab.rb
RUN  perl -pi.bak -e "s/letsencrypt\[[']contact_emails[']\] = \[\]/letsencrypt\[\'contact_emails\'\] = \[\'laza.mar64\@gmail.com\'\]/g" /etc/gitlab/gitlab.rb

# RUN ufw allow http 
# && ufw allow https && ufw allow OpenSSH



# RUN gitlab-ctl reconfigure


# EXPOSE 3000
# CMD ["gitlab", "s", "-b", "0.0.0.0", "-p", "3000"]

# next steps
# RUN apt install letsencrypt -y && letsencrypt certonly --standalone\
#  --agree-tos --no-eff-email --agree-tos --email laza.mar64@gmail.com -d git.marrodri-labs.pw

# RUN mkdir -p /etc/gitlab/ssl && openssl dhparam -out /etc/gitlab/ssl/dhparams.pem 2048 && chmod 600 /etc/gitlab/ssl/*



# 'http://gitlab.example.com'