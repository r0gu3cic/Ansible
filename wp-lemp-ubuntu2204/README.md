Wordpress on LEMP (Linux, Nginx, MySQL, PHP) on Ubuntu 22.04 LTS

This playbook will install a WordPress website on top of a LEMP environment (Linux, Nginx, MySQL and PHP) on an Ubuntu 22.04 server. 
This is POC and minimalistic approach, but it is working.
A virtualhost will be created with the options specified in the vars/default.yml variable file.

Options
mysql_root_password: The desired password for the root MySQL account.
mysql_db: The name of the MySQL database that should be created for WordPress.
mysql_user: The name of the MySQL user that should be created for WordPress.
mysql_password: The password for the new MySQL user.
http_host: Your domain name.
http_conf: The name of the configuration file that will be created within Apache.
http_port: HTTP port for this virtual host, where 80 is the default.

1. Obtain the playbook
git clone https://github.com/r0gu3cic/ansible-projects/wp-lemp-ubuntu2204.git
cd ansible-projects/wp-lemp-ubuntu2204

2. Customize Options
nano vars/default.yml

#MySQL setings
mysql_root_password: "mysqlrootpassword"
mysql_db: "wordpress"
mysql_user: "wordpress"
mysql_password: "password"
#HTTP setings
http_host: "hostname"
http_conf: "wordpress.conf"
http_port: "80"

3. Run the Playbook
ansible-playbook playbook.yml -l [target] -u [sudo user on target] --extra-vars 'ansible_become_pass=[sudo user password]'
