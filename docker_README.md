### Docker -container with ansible:

      Prerequisite:
      
              yum install -y docker && service docker start 
              yum install -y python python-pip && pip install docker_py 
              docker login : (with credentials)
              
 ### Docker run command in ansible:
 
            - hosts: localhost
              tasks:
              - name: create
                docker_container:
                  name: webappcontainer
                  image: klogambigai/stackdemo:latest
                  state: started
                  recreate: yes
                  ports:
                  - 8000:8000
                tags: create

### Docker rm and docker stop container:


                - name: remove
                  docker_container:
                    name: webappcontainer
                    image: klogambigai/stackdemo:latest
                    state: absent
                    recreate: yes
                    exposed_ports:
                    - 8000:8000
                  tags: remove



![image](https://user-images.githubusercontent.com/54719289/107370790-706cfa80-6b09-11eb-8d38-410b27b17fcc.png)

![image](https://user-images.githubusercontent.com/54719289/107370159-9d6cdd80-6b08-11eb-9ab8-fd6d871ca60f.png)
