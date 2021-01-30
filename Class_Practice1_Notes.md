#  Ansible playbook Commands:
    # update_cache=yes ==> tells Ansible’s apt module to refresh the caches before applying whatever change is necessary (if any).
      
      ---
      - hosts: webserver
        tasks:
            - name: install nginx
              apt: name=nginx state=present update_cache=yes
   
 ![image](https://user-images.githubusercontent.com/54719289/106364947-53416a80-6358-11eb-844a-d39680d1d230.png)

      - Installed in ubuntu node but failed in linux node machine:
      
 ![image](https://user-images.githubusercontent.com/54719289/106365074-1a55c580-6359-11eb-8038-56781c95f37d.png)
      
      
      
        # stat  :retrieve file or file system status

    it determines if yum path exists or not, if exists install git in linux or else it skips linux and install in ubuntu
 ![image](https://user-images.githubusercontent.com/54719289/106366130-cf8b7c00-635f-11eb-9a9d-c0803f56edb1.png)
    
![image](https://user-images.githubusercontent.com/54719289/106366074-93581b80-635f-11eb-8f59-e86444cd6565.png)    
    
 
 # The below code skips installing if git already exists,
 
 ![image](https://user-images.githubusercontent.com/54719289/106366340-39f0ec00-6361-11eb-8dd5-3fa0526abd85.png)
 ![image](https://user-images.githubusercontent.com/54719289/106366328-22b1fe80-6361-11eb-9f29-0cde80a18e99.png)
 
 
 # To copy the master ssh key into another machine use below script,
        #!/bin/bash
        for ip in `cat /home/list_of_servers`; do
            ssh-copy-id -i ~/.ssh/id_rsa.pub $ip
        done
    
 

#   For different OS:

![image](https://user-images.githubusercontent.com/54719289/106369971-053e5e00-637c-11eb-9d41-18a09a72d29b.png)

    
    


