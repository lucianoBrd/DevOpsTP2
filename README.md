# sample-application-students
This is a sample application Springboot - Vue - Postgres Student application 

## Backend
Simple Rest API Server

## Frontend
Simple Vue.js Client

## Database
Simple Postgres 9 Database

# TP 2 CI/CD

## Sample project

```sh
docker compose up # runs docker-compose.yml which seeks for Dockerfiles and executes various commands to run the required containers
```
- Check ```localhost``` ***(beware of cache, ran in private browser)***

## Travis CI
- Language : YAML *(just like many others)*

- Alternatives :
    - Jenkins (less accessible, more customizable)
        - Language : Groovy
    - Gitlab CI
    - Bitbucket Pipeline

### Build and test your applcation

- Build the app thanks to the ```pom.xml``` file

- Test containers : containers run for tests

- 2 stages : 1 for java, the other is for node
    - for java tests : detected Maven thanks to pom.xml
    - node : detected thanks to language (npm is to be used)

- **BEWARE OF YAML INDENTS !!**

## DockerHub, Travis-CI & CD

- We need a develop branch because master is for production

- Add env variables in Travis : name referenced as ```$VAR_NAME``` in .travis.yml **(case sensitive)**

## Setup Quality Gate

- Create SONARCLOUD_TOKEN in Travis-CI website

# TP 3 ansible

```ansible all -i ansible/inventories/setup.yml -m ping```
```ansible-playbook -i ansible/inventories/setup.yml ansible/playbook.yml```
```ansible-galaxy init ansible/roles/database```

# Docker images :

* https://hub.docker.com/repository/docker/lucianobrd/backend
* https://hub.docker.com/repository/docker/lucianobrd/frontend

# GitHub

* https://github.com/lucianoBrd/DevOpsTP2