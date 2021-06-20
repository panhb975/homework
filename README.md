# homework
[homework](https://github.com/panhb975/homework) is a simple ASP.NET Core Web application, the purpose for creating it is to demo. 
## branches
- main branch for release
- develop branch for daily development
## ci yml file
.github\workflows\homework.yml
- trigger condition: push on develop branch; pull request on develop or main branches
- build project
- build docker image
- push docker image to [docker hub](https://hub.docker.com/repository/docker/hongbiao/homework)
## Dockerfile
Dockerfile\Dockerfile
## chart file
charts\values.yml
After run "kubectl apply -f values.yml" in AKS, homework can be accessed, like http://20.89.82.50:8077/
## security info
docker login user and password are used when push image to Docker Hub, they are stored in  https://github.com/panhb975/homework/settings/secrets/actions



