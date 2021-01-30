# Ansible

    Instead of installing software manually in client/server machine manually will be using ansible for that in automated way.
    
    For example: Need to install java and Maven in multiple machin, we can use ansible.
    
    But with ansible just do the 
      >>  ssh setup between master and client machine where you want to do the configuration in automated way.
      >> create inventory file or host file which will be understanable by ansible and it will connect to those server and perform tasks.
    
    Creating three servers:
    ====================  
      server 1    ===> master
      server 2 ,3 ==> node
      
   # Steps:
        Step 1:   Generate ssh key on master and copy pub key of master to all node/client/slave machines.
    
 ![image](https://user-images.githubusercontent.com/54719289/106311056-89181d80-628a-11eb-9d57-76b1016b0b95.png)
 ![image](https://user-images.githubusercontent.com/54719289/106311141-ad73fa00-628a-11eb-8e34-829314b727de.png)
      
 ![image](https://user-images.githubusercontent.com/54719289/106311724-9b468b80-628b-11eb-8184-88bb082de99c.png)
 ![image](https://user-images.githubusercontent.com/54719289/106311753-a4cff380-628b-11eb-9045-43a35fc0f22a.png)
 ![image](https://user-images.githubusercontent.com/54719289/106311800-b5806980-628b-11eb-8291-0f9ec73ab88d.png)
  
  Check if you are able to login node1 and node2 from master with ssh:
  
 ![image](https://user-images.githubusercontent.com/54719289/106312112-30498480-628c-11eb-840b-d9371152e6cc.png)
 ![image](https://user-images.githubusercontent.com/54719289/106312201-51aa7080-628c-11eb-933f-9d53fb63d451.png)



        Step 2:   Install ansible only on master and not on nodes
        
        In master:
        
            amazon-linux-extras install ansible2
 
![image](https://user-images.githubusercontent.com/54719289/106312585-e8772d00-628c-11eb-9255-ebf0cfb48b3d.png)
![image](https://user-images.githubusercontent.com/54719289/106312542-d4333000-628c-11eb-8f50-504547d471e4.png)

        Step 3:   create inventory file(either in /stc/ansible/ or in your local path-->name of the file -hosts) for mentioning the ipaddr of node machine
                  
                  /etc/ansible/hosts -- is called inventory file
        
                  -- We will create a grouping 
                  
                    [webservers]
                    node1ip
                    node2ip

![image](https://user-images.githubusercontent.com/54719289/106312885-5b80a380-628d-11eb-8d9c-b7529cf408d7.png)

                  -- its possible to give domain name in inventory file but location should be placed in /etc/hosts
        
        
        Step 4: Check with ping command in ansible for webservers connection
        
 ![image](https://user-images.githubusercontent.com/54719289/106313478-48220800-628e-11eb-876f-c230371f2ce1.png)


        Step 5: Play with Ansible adhoc commands for better understanding
        
         (Sample adhocs are >> Rebooting server >>managing files >> Managing Packages >> Managing user & groups >> Managing services >>Gathering facts)
         
         Sample adhoc for java installation:

        command: ansible -m yum -a 'name=java-1.8.0-openjdk state=present' webservers
       
![image](https://user-images.githubusercontent.com/54719289/106314154-53c1fe80-628f-11eb-9126-f1d6a2680af9.png)


        get_url:    ansible -m get_url -a 'url=https://downloads.apache.org/tomcat/tomcat-8/v8.5.61/bin/apache-tomcat-8. dest=/opt mode=0777' webservers

        unarchive:  ansible -m unarchive -a 'src=/opt/apache-tomcat-8.5.61.tar.gz dest=/opt remote_src=yes' webservers

         
 # Install httpd with ansible-playbook
 
  1.    create install_httpd.yml and check the syntax check
    
    
  ![image](https://user-images.githubusercontent.com/54719289/106318868-920eec00-6296-11eb-9cff-ab7b7874d7e5.png)

  
  After correction:
  
  ![image](https://user-images.githubusercontent.com/54719289/106319059-de5a2c00-6296-11eb-811d-20f749006758.png)

 2  Run :
  
  ansible-playbook install_httpd.yml

![image](https://user-images.githubusercontent.com/54719289/106319284-3729c480-6297-11eb-8c37-b92c9c76be88.png)

3.  Service start added in install_httpd.yml:

![image](https://user-images.githubusercontent.com/54719289/106320148-74428680-6298-11eb-8b6c-b72ff16c4778.png)


# For tomcat ---> place the tomcat.service under the folder where your ansible yml is saved.

Or else will get the below error,

![image](https://user-images.githubusercontent.com/54719289/106330852-fe471b00-62a9-11eb-8851-7c3b4711e8de.png)


![image](https://user-images.githubusercontent.com/54719289/106330616-8d9ffe80-62a9-11eb-8cd0-46e5c9965884.png)


# Check the tomcat service in node:

![image](https://user-images.githubusercontent.com/54719289/106330665-a0b2ce80-62a9-11eb-9df5-26933069d7b5.png)


# ansible_practice1.yml:

    - name: sample
      hosts: webservers
      remote_user: root   ===> remote user is root
      become: true        ===>  allowing root user to execute this playbook, if false then permission denied to remote user for execution 


---
- name: sample
  hosts: webservers
  remote_user: root
  become: false
  tasks:
     - name: install
       yum :
             name: maven
             state: latest
     - name: Checking
       command: echo 'Heloo'


# Execute with -v so that we could see the echo command:
    
    Command: ansible-palybook -v ansible_practice1.yml --syntax-check
    
    
![image](https://user-images.githubusercontent.com/54719289/106362962-b24cb280-634b-11eb-9ebc-05b1d90fa6d9.png)

![image](https://user-images.githubusercontent.com/54719289/106362923-7dd8f680-634b-11eb-9266-189197fe0298.png)



      
      








    

