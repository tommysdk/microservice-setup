# microservice-setup

To make it easy to get started with this project, we provide the option to run Jenkins with Jenkins Job Builder as a Docker container. In a real life scenario you would obviously use a proper Jenkins installation. To use the provided dockerized Jenkins, follow the instructions below. If you use your own Jenkins installation you need to have Jenkins Job Builder installed. Perform the corresponding jenkins-jobs commands using your Jenkins Job Builder installation with the appropriate settings in jenkins_jobs.ini to allow access to your Jenkins instance.

## Setup Jenkins
Build and run
```
docker build -t jjb jenkins/
docker run -d -v $PWD/jenkins/jjb:/etc/jenkins_jobs -v ~/.aws:/var/jenkins_home/.aws -v ~/.m2:/var/jenkins_home/.m2 -p 8080:8080 --name jjb jjb
```

Browse to: http://localhost:8080 and complete the Jenkins install procedure using the recommended plugin setup
Find the admin password by running:
```
docker exec jjb cat /var/jenkins_home/secrets/initialAdminPassword
```

Setup Jenkins Job Builder by running:
```
sed "s/PASSWORD/$(docker exec jjb cat /var/jenkins_home/secrets/initialAdminPassword)/" jenkins/jjb/jenkins_jobs.ini.template jenkins/jjb/jenkins_jobs.ini
```

Seed Jenkins with the necessary job configurations:
```
docker exec jjb jenkins-jobs update /etc/jenkins_jobs/job-configurations.yml
```
