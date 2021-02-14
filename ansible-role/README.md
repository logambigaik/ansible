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

