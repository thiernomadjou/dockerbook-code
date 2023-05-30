FROM jenkins/jenkins:2.346.3-jdk11
MAINTAINER james@example.com
ENV REFRESHED_AT 2016-06-01

USER root
RUN apt-get -qq update && apt-get install -qq sudo && apt-get install -yqq wget
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
RUN wget http://get.docker.com/builds/Linux/x86_64/docker-latest.tgz
RUN tar -xvzf docker-latest.tgz
RUN mv docker/* /usr/bin/

USER jenkins
RUN  jenkins-plugin-cli --plugins "junit git git-client ssh-slaves greenballs chucknorris ws-cleanup"
