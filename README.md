# microservice-setup

## Setup Jenkins
## Build and run
```
docker build -t jjb jenkins/
docker run -d -v $PWD/jjb:/jenkins-job-config -p 8080:8080 --name jjb jjb
```

Browse to: http://localhost:8080 and complete the Jenkins install procedure using the recommended plugin setup

Find the admin password by running:
```
docker exec jjb cat /var/jenkins_home/secrets/initialAdminPassword
```

Setup Jenkins Job Builder by running:
```
sed "s/PASSWORD/$(docker exec jjb cat /var/jenkins_home/secrets/initialAdminPassword)/" jenkins/jenkins_jobs.ini
```

Seed Jenkins with the necessary job configurations:
```
docker exec jjb jenkins-jobs update /jenkins-job-config/job-configurations.yml
```
