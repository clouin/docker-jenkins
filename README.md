# Docker 中的 Jenkins

在 Jenkins 容器中运行 Docker

## 如何使用

```
docker run -it -p 8080:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock -v path/to/jenkins_home:/var/jenkins_home jerryin/jenkins-docker
```

运行上述命令后，访问 localhost:8080 来配置您的 Jenkins 环境。

或者 docker-compose

```
version: "3"

services:
  jenkins:
    image: jerryin/jenkins-docker
    restart: unless-stopped
    ports:
      - 8005:8080
      - 50000:50000
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - ./jenkins_home:/var/jenkins_home
    environment:
      - TZ=Asia/Shanghai
```
