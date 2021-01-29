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
        
        Step 2:   Install ansible only on master and not on nodes
        
        Step 3:   create inventory file(either in /stc/ansible/ or in your local path-->name of the file -hosts) for mentioning the ipaddr of node machine
                  
                  /etc/ansible/hosts -- is called inventory file
        
                  -- We will create a grouping 
                  
                    [webservers]
                    node1ip
                    node2ip
                    
                  -- its possible to give domain name in inventory file but location should be placed in /etc/hosts
        
        
      
    
![image](https://user-images.githubusercontent.com/54719289/106304735-bca27a00-6281-11eb-9960-5ba8e92fb40f.png)
