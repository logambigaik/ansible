# Prerequiste:

    Python3
    pip3
    docker
    docker-compose
    
#    Install using https://github.com/logambigaik/ansible/blob/main/docker-container/docker-compose/install_python_docker_coker_compose.yml

# docker -compse up in ansible:

        - hosts: localhost
          tasks:
          - name: Run docker-compose up
            docker_compose:
              project_src: /root/Dockerpostgres
              state: present
            register: output
            tags: up
            
 #  ansible-playbook -v doc_compose_ansible.yml
     Throw below error,
     
  ![image](https://user-images.githubusercontent.com/54719289/107788810-d90cdf00-6d76-11eb-8d7b-bd7d76935a3c.png)


    by default , ansible picks python2 interpreter, so we need to pass python3
    
# ansible-playbook -v doc_compose_ansible.yml -e ansible_python_interpreter=/usr/bin/python3 or else update the intrepreter in playbook using vars



![image](https://user-images.githubusercontent.com/54719289/107789008-11acb880-6d77-11eb-9359-ca962c1ac466.png)



# ansible interpreter in playbook:

![image](https://user-images.githubusercontent.com/54719289/107789119-34d76800-6d77-11eb-9e6f-853bda6f3f42.png)



     
     
