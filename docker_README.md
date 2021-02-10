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


# docker -run for postgres:

        
![image](https://user-images.githubusercontent.com/54719289/107574924-3be66500-6c15-11eb-831f-f97ceccab41d.png)
![image](https://user-images.githubusercontent.com/54719289/107575042-63d5c880-6c15-11eb-8bb2-15c4f3313606.png)
![image](https://user-images.githubusercontent.com/54719289/107575147-8ec01c80-6c15-11eb-92b8-832b7daf5ce5.png)


#  Ansible-vault --> it helps to protect the password in encrypt format

![image](https://user-images.githubusercontent.com/54719289/107578013-32f79280-6c19-11eb-888f-e10876ac4f03.png)

            Step1 :For that created password.yml and the password in key value format,
            
            for example:
              postgres_pwd:Password1
              
            
            Step 2: ansible-vault encrypt password.yml (provide password for ansible-vault-test123)
            
 ![image](https://user-images.githubusercontent.com/54719289/107578527-d9dc2e80-6c19-11eb-8b47-a4341e15dd56.png)
 ![image](https://user-images.githubusercontent.com/54719289/107578565-e791b400-6c19-11eb-9794-84d5b34cae59.png)


            Step3: Use that value in docker_container file:
 ![image](https://user-images.githubusercontent.com/54719289/107578690-127c0800-6c1a-11eb-993b-bbfc09242824.png)
 

# with var variable:

 ![image](https://user-images.githubusercontent.com/54719289/107579226-d2695500-6c1a-11eb-8a8d-0e2946e1ebc2.png)

      ansible-playbook -v psql.yml --tags=create
      
 ![image](https://user-images.githubusercontent.com/54719289/107579346-f9c02200-6c1a-11eb-99a8-7fdbd2604992.png)

# with password.yml:

      COmmand:       ansible-playbook -v --ask-vault-pass psql.yml --tags=create

      if there is no space after key like postgres_pwd:Password1 then , we will get below error
      
 ![image](https://user-images.githubusercontent.com/54719289/107580037-0133fb00-6c1c-11eb-833f-21a46e751fe7.png)

            it should be postgres_pwd: Password1.
      
      -            
            
![image](https://user-images.githubusercontent.com/54719289/107580157-29235e80-6c1c-11eb-8c3c-e694a1a837ea.png)
![image](https://user-images.githubusercontent.com/54719289/107580201-38a2a780-6c1c-11eb-8cce-39e17b1e7fd6.png)



# with password file and instead ask-vault usigs --vault-password-file:

      [root@ip-172-31-49-130 Dockerpostgres]# ansible-playbook -v psql.yml --vault-password-file=test.yml --tags=create

      FOr that create test.yml to save vault password and pass the same while running ansible command.
      
![image](https://user-images.githubusercontent.com/54719289/107581100-9a174600-6c1d-11eb-9830-736e8f8c5062.png)
      
![image](https://user-images.githubusercontent.com/54719289/107580944-63d9c680-6c1d-11eb-82f7-600e9eafa388.png)
![image](https://user-images.githubusercontent.com/54719289/107580973-6e945b80-6c1d-11eb-9686-2fd385d0e44a.png)


![image](https://user-images.githubusercontent.com/54719289/107581398-085c0880-6c1e-11eb-8b6a-723724184809.png)




            
            
            
            


