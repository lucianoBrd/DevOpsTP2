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

```yaml
---
"{{ Ansible }}" is an orchestration tool written in Python.
...
```

Ansible is (one of many) orchestration tools. It allows you to control your
environment (infrastructure and code) and automate the manual tasks.

Ansible has great integration with multiple operating systems (even Windows)
and some hardware (switches, Firewalls, etc). It has multiple tools that
integrate with the cloud providers. Almost every noteworthy cloud provider is
present in the ecosystem (AWS, Azure, Google, DigitalOcean, OVH, etc...).

But ansible is way more! It provides execution plans, an API, library, and callbacks.

## Installation

```bash
# Universal way
$ pip install ansible

# Debian, Ubuntu
$ apt-get install ansible
```

* [Appendix A - How do I install ansible](#infrastructure-as-a-code)
* [Additional Reading.](http://docs.ansible.com/ansible/latest/intro_installation.html)

## Your first ansible command (shell execution)

```bash
# Command pings localhost (defined in default inventory: /etc/ansible/hosts)
$ ansible -m ping localhost
# You should see this output
localhost | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

## Shell Commands

There are few commands you should know about

* `ansible` (to run modules in CLI)
* `ansible-playbook` (to run playbooks)
* `ansible-vault` (to manage secrets)
* `ansible-galaxy` (to install roles from github/galaxy)

## Task

Execution of a single Ansible **module** is called a **task**. The simplest
module is called `ping` as you could see above.

Another example of the module that allows you to execute a command remotely on
multiple resources is called `shell`. See above how you were using them already.

## Playbook

**Execution plan** written in a form of script file(s) is called **playbook**.
Playbooks consist of multiple elements -
* a list (or group) of hosts that 'the play' is executed against
* `task(s)` or `role(s)` that are going to be executed
* multiple optional settings (like default variables, and way more)

Playbook script language is YAML. You can think that playbook is very advanced
CLI script that you are executing.

## ansible-roles

You already know that the tasks (modules) can be run via CLI. You also know the
playbooks - the execution plans of multiple tasks (with variables and logic).

A concept called `role` was introduced for parts of the code (playbooks) that
should be reusable.

**Role** is a structured way to manage your set of tasks, variables, handlers,
default settings, and way more (meta, files, templates). Roles allow reusing
the same parts of code in multiple playbooks (you can parametrize the role
'further' during its execution). Its a great way to introduce `object oriented`
management for your applications.

Role can be included in your playbook (executed via your playbook).

## Commands
En cas de problème enlever host SSH ```ssh-keygen -R "lucien.burdet.takima.cloud"```

```ansible all -i ansible/inventories/setup.yml -m ping```
```ansible-playbook -i ansible/inventories/setup.yml ansible/playbook.yml```
```ansible-galaxy init ansible/roles/database```

# Docker images :

* https://hub.docker.com/repository/docker/lucianobrd/backend
* https://hub.docker.com/repository/docker/lucianobrd/frontend

# GitHub

* https://github.com/lucianoBrd/DevOpsTP2