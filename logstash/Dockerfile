# https://github.com/elastic/logstash-docker
FROM ubuntu:17.10

USER 0

RUN apt-get update
RUN apt-get -y install software-properties-common
RUN add-apt-repository ppa:webupd8team/java
RUN apt-get update
RUN echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 select true" | debconf-set-selections
RUN apt-get -y install oracle-java8-installer
RUN apt-get -y install oracle-java8-set-default

RUN apt-get -y install git

RUN apt-get -y install ruby-full
RUN gem install rake
RUN gem install bundler

WORKDIR /
RUN git clone -b 5.6 https://github.com/elastic/logstash.git
WORKDIR /logstash

RUN rake bootstrap
RUN rake test:install-core
RUN bin/logstash-plugin install --development

# COPY /pattern /etc/logstash/pattern
# COPY /filter project_spec/filter
# COPY /test project_spec/test
# COPY /suite_runner.rb project_spec

# CMD ["top -b"]