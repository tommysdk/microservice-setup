# microservice-setup

## Run dev jenkins
```
docker build -t jjb .
ocker run -v $PWD/jjb:/jenkins-job-config -it -p 8080:8080 jjb /bin/bash
Browse to: http://localhost:8080
```
