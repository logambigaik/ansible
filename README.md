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
![image](https://user-images.githubusercontent.com/54719289/106312542-d4333000-628c-11eb-8f50-504547d471e4.png

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

         
         
        
        
                
    
![image](https://user-images.githubusercontent.com/54719289/106304735-bca27a00-6281-11eb-9960-5ba8e92fb40f.png)
