# microservice-setup

## Run dev jenkins
```
docker build -t jjb .
docker run -v $PWD/jjb:/jenkins-job-config -d -p 8080:8080 jjb
```

Browse to: http://localhost:8080
Find admin password by running:
```
docker exec jjb cat /var/jenkins_home/secrets/initialAdminPasswor
```
