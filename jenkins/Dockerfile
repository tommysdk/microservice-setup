FROM jenkins:1.651.3
MAINTAINER "Tommy Tynjä"

USER root
RUN apt-get update && apt-get install -y php5-mcrypt python-pip
RUN pip install PyYAML python-jenkins jenkins-job-builder
USER jenkins
