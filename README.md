# ansible-nginx-role
This repo represents ngin role combined with some features to show some good examples of Ansible which is our final aim. Along with nginx, we added a base role that creates groups and users and we show how we can integrate different roles together.
This role is deployed in /etc/ansible/roles and it will be invoked in another file called ww.yml:

www.yml
#www.yml : playbook for web servers
- hosts: www
  remote_user: ansible
  sudo: yes
  pre_tasks:
    - shell: echo 'I":" Beginning to configure web server..'
  roles:
    - nginx
  post_tasks:
    - shell: echo 'I":" Done configuring nginx web server..'
    
  The previous code uses a a syntax that will be depracated soon. You can run yourself to see what are the depracated blocs.
