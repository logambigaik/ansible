### Docker -container with ansible:

      Prerequisite:
      
              yum install -y docker && service docker start 
              yum install -y python python-pip && pip install docker_py 
              docker login : (with credentials)
 ![image](https://user-images.githubusercontent.com/54719289/107371914-d7d77a00-6b0a-11eb-8ca1-28170a70f72b.png)
 
 
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


# Docker healthcheck:
            # With simplewebapp
![image](https://user-images.githubusercontent.com/54719289/107376134-8aa9d700-6b0f-11eb-9dcb-1b28f8b7f193.png)  


            # with link:
            
  
![image](https://user-images.githubusercontent.com/54719289/107379258-c1cdb780-6b12-11eb-912e-658c4868ddc2.png)

            # WIthout link:
            
 WIthout redis(links):

![image](https://user-images.githubusercontent.com/54719289/107379867-5b956480-6b13-11eb-9f6b-0b9fe7a2875a.png)

            If there is any link,run that image before doing healthcheck:
            
  ![image](https://user-images.githubusercontent.com/54719289/107380123-97c8c500-6b13-11eb-9234-2bbee4b276c1.png)



