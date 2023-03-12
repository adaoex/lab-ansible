# Lab Ansible
docs: https://www.ansible.com/resources/get-started

## Docker containers

* Control
* Node1
* Node2

## RUN control

```
docker compose up -d

docker compose exec -it control bash

cd /root/ansible

ansible -i hosts all -m ping

ssh-keygen

ssh-copy-id root@node1
```

**hosts(localhost)**

localhost ansible_connection=local

## RUN node1

```
docker compose exec -it node1 bash

service ssh start

```

## Samples

```
# install
ansible -i hosts all -m apt -a "update_cache=yes name=nginx state=present"
ansible -i hosts all -m apt -a "update_cache=yes name=git state=present"

# remove
ansible -i hosts all -m apt -a "update_cache=yes name=nginx state=absent"
ansible -i hosts all -m apt -a "update_cache=yes name=git state=absent"
```
