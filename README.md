# jenkinsci
A simple Jenkins CI setup to deploy app in to K8 cluster


### Bring up Jenkins using below command
`docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_data:/var/jenkins_home jenkins/jenkins:lts`

### Install below plugins
```
kubernetes
kubernetes continuous deploy 
```