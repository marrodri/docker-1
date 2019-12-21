
# Your generic container should install, via a ruby container, 
# all the necessary dependencies and gems, then copy your rails application in the /opt/app folder of your
# container. Docker has to install the approtiate gems when it builds, but also launch
# the migrations and the db population for your application. The child Dockerfile should
# launch the rails server (see example below). If you don’t know what commands to use,
# it’s high time to look at the Ruby on Rails documentation.

FROM ruby:2.6.2
RUN apt-get update && apt-get install -y \
build-essential \
nodejs \
gem

ONBUILD WORKDIR /opt/apt
ONBUILD COPY hello_world_app ./

ONBUILD RUN gem install rails bundler rake \
&& bundler update

# RUN bundle install --deployment --without development test
ONBUILD RUN rake db:create
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
ONBUILD EXPOSE 3000
# RUN rails server


# CMD ["rails", "s", "-b", "0.0.0.0", "-p", "3000"]
# ENTRYPOINT ./entrypoint.sh
# ONBUILD WORKDIR /opt/apt
# ONBUILD COPY ../hello_world_app /opt/apt
# ONBUILD RUN rake db:create
# ONBUILD RUN rails server
# docker run -d --name test -p 3000:3000 hello_world_app