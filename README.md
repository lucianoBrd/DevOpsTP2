# sample-application-students
This is a sample application Springboot - Vue - Postgres Student application 

## Backend
Simple Rest API Server

## Frontend
Simple Vue.js Client

## Database
Simple Postgres 9 Database

## ansible
ansible all -i ansible/inventories/setup.yml -m ping
ansible-playbook -i ansible/inventories/setup.yml ansible/playbook.yml 
ansible-galaxy init ansible/roles/database