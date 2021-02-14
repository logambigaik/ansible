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
        ansible-galaxy init /etc/ansible/roles/apache --offline
        
![image](https://user-images.githubusercontent.com/54719289/107889390-40be5800-6f38-11eb-9a55-56a021c5c739.png)

![image](https://user-images.githubusercontent.com/54719289/107889449-add1ed80-6f38-11eb-9664-9540b3bb3b88.png)


# First inside tasks folder create install.yml and configure.yml and in files folder copy the httpd config and our updated index.html from httpd.

![image](https://user-images.githubusercontent.com/54719289/107889891-91838000-6f3b-11eb-910d-000410c72703.png)

