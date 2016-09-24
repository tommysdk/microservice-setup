FROM jenkins:2.7.4
MAINTAINER "Tommy Tynjä"

USER root
RUN apt-get update && apt-get -y --no-install-recommends install php5-mcrypt python-pip maven
RUN pip install PyYAML python-jenkins jenkins-job-builder awscli
USER jenkins

