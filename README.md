# Ansible Drone Plugin

an ansible container to be used as drone.io cicd pipeline plugin for testing ansible-playbooks.

# Examples 

## example .drone.yml:

    pipeline:
      test-ansible-playbook:
        image: jpduyx/drone-plugin-ansible:latest
        commands:
        - cd tst
        - chmod -R 0600 keys/id_rsa*
        - pwd
        - ansible-playbook --private-key="keys/id_rsa"    myplaybook.yml 

## example manual usage
With this command you enter the container and you'll find your playbook mounted in /ansible/playbooks

  docker run --rm -it -v /absolute/path/to/playbook/folder:/ansible/playbooks jpduyx/drone-plugin-ansible /bin/sh

  
  
# Docker Hub: 

https://hub.docker.com/r/jpduyx/drone-plugin-ansible
