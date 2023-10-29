<img src="https://img.shields.io/badge/language-DockerCompose-blue.svg"/> <img src="https://img.shields.io/github/last-commit/vmzcloud/DockerCompose_Gitea.svg"/>

# Gitea

![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Gitea_Logo.svg/240px-Gitea_Logo.svg.png "Gitea")

[Reference](https://docs.gitea.com/installation/install-with-docker)

## docker-compose.yml
```
version: "3"

networks:
  gitea:
    name: gitea

services:
  server:
    image: gitea/gitea:1.20
    container_name: gitea
    hostname: gitea
    environment:
      - USER_UID=1000
      - USER_GID=1000
    restart: always
    networks:
      - gitea
    volumes:
      - ./gitea/repositories:/data/git/repositories
      - ./gitea:/data
      - /etc/timezone:/etc/timezone:ro
      - /etc/localtime:/etc/localtime:ro
    ports:
      - "3000:3000"
```

## Setup
![Initial_Config](https://github.com/vmzcloud/DockerCompose_Gitea/assets/69754738/bb7c66d2-5e00-4abe-92ec-efba3eaeb0ad)

![General_Settings](https://github.com/vmzcloud/DockerCompose_Gitea/assets/69754738/622a9d73-f57b-4eb8-a76b-1306efd2ad23)

![Optional_Settings](https://github.com/vmzcloud/DockerCompose_Gitea/assets/69754738/bf35e451-081c-47a4-adcd-c6946c042c57)
