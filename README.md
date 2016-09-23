# microservice-setup

## Run dev jenkins
```
docker build -t jjb .
ocker run -v $PWD/jjb:/jenkins-job-config -d -p 8080:8080 jjb
Browse to: http://localhost:8080
```
