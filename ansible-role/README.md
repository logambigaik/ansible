Link: https://www.learnitguide.net/2018/02/ansible-roles-explained-with-examples.html
 
# Manual process for http:

        >> Install httpd 
        >> Configure httpd
        >> Start httpd 
  
 
  # Conf file present in: /etc/httpd/conf/httpd.conf
  
  Search DocumentRoot to update the index page:
  
  DocumentRoot "/var/www/html"

  ![image](https://user-images.githubusercontent.com/54719289/107888057-5f205580-6f30-11eb-94c8-7ee1432ae694.png)

  # To know the index file:
  
        [root@ip-172-31-90-165 conf]# cat /etc/httpd/conf/httpd.conf | grep DirectoryIndex
        # DirectoryIndex: sets the file that Apache will serve if a directory
        DirectoryIndex index.html
        
 ![image](https://user-images.githubusercontent.com/54719289/107889262-64cd6980-6f37-11eb-8ab8-11890fd3e247.png)


# Creating ansible roles run below command : 
        ansible-galaxy init /etc/ansible/roles/apache --offline    ==>here apache is nmae of the role
        
![image](https://user-images.githubusercontent.com/54719289/107889390-40be5800-6f38-11eb-9a55-56a021c5c739.png)

![image](https://user-images.githubusercontent.com/54719289/107889449-add1ed80-6f38-11eb-9664-9540b3bb3b88.png)


# First inside tasks folder create install.yml and configure.yml and in files folder copy the httpd config and our updated index.html from httpd.



refer loga-ansiblerole.git

!![image](https://user-images.githubusercontent.com/54719289/107889930-e1fadd80-6f3b-11eb-8144-55557cbd906c.png)

![image](https://user-images.githubusercontent.com/54719289/107889955-1078b880-6f3c-11eb-8427-07108d2357d7.png)

![image](https://user-images.githubusercontent.com/54719289/107890025-82e99880-6f3c-11eb-8b56-863770642f57.png)


# Update main.yml in tasks,handles and meta folder:

![image](https://user-images.githubusercontent.com/54719289/107890211-a82ad680-6f3d-11eb-8daa-c753093a53ce.png)


# Linux command for find and replace:

grep -rli 'old-word' * | xargs -i@ sed -i 's/old-word/new-word/g' @

grep -rli 'loga' * | xargs -i@ sed -i 's/loga/loga-ansiblerole/g' @
