Jinja2 Templates in Ansible Playbook:
====================================

https://www.linuxtechi.com/?s=ansible

Jinja2 templates are simple template files that store variables that can change from time to time. When Playbooks are executed, these variables get replaced by actual values defined in Ansible Playbooks. 
This way, templating offers an efficient and flexible solution to create or alter configuration file with ease.

Template architecture
A Jinja2 template file is a text file that contains variables that get evaluated and replaced by actual values upon runtime or code execution. 
In a Jinja2 template file, you will find the following tags:

      {{ }}  : These double curly braces are the widely used tags in a template file and they are used for embedding variables and ultimately printing their value during code execution. For example, a simple syntax using the double curly braces is as shown: The {{ webserver }} is running on  {{ nginx-version }}
      {%  %} : These are mostly used for control statements such as loops and if-else statements.
      {#  #} : These denote comments that describe a task.
      
 # Jinja2-template file : example.j2 
 
      Hey guys!
      Apache webserver {{ version_number }} is running on {{ server }}
      Enjoy!
      
      Here, the variables are {{ version_number }} & {{ server }
   
      ansible-jinja.yml
      ------------------
      
      ---
      - hosts: localhost
      vars:
        version_number: '2.4.37'
        server: 'Ubuntu'
      tasks:
      - name: Jinja2 template example
        template:
          src: example.j2
          dest: file1.txt

        See the change in file1.txt
        
 # For example:
 
  ![image](https://user-images.githubusercontent.com/54719289/107861662-531f8f80-6e6d-11eb-954a-8643f01c766d.png)
