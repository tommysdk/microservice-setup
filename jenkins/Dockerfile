FROM jenkins:2.7.4
MAINTAINER "Tommy Tynjä"

USER root
RUN apt-get update && apt-get install -y php5-mcrypt python-pip awscli maven
RUN pip install PyYAML python-jenkins jenkins-job-builder
USER jenkins

