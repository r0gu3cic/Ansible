WordPress on LEMP (Linux, Nginx, MySQL, PHP) on Ubuntu 22.04 LTS

I am starting my DevOps journey, as I have learned how to set up a WordPress site on Linux Server, I wanted to automate the process using ansible.
This ansible-playbook help me deploy WordPress and LEMP environment fast to the new bare-metal Linux server.
With this project, I have learned a little bit about ansible, CM, Nginx, and Linux in general.
This is only a POC, this is not a production-ready server configuration.

Options in var/default.yml:
- mysql_root_password: The desired password for the root MySQL.
- mysql_db: The name of the MySQL database that should be created for WordPress.
- mysql_user: The name of the MySQL user that should be created for WordPress.
- mysql_password: The password for the new MySQL user.
- http_host: Your domain name.
- http_conf: The name of the configuration file that will be created within Nginx.
- http_port: HTTP port for this virtual host, where 80 is the default.

Usage:
1. Obratin the playbook
```
git clone https://github.com/r0gu3cic/ansible-projects.git
```
```
cd ansible-projects/wp-lemp-ubuntu2204
```

2. Customize options
```
nano vars/default.yml
```

3. Run the playbook
```
ansible-playbook playbook.yml -l [target] -u [sudo user on target] --extra-vars 'ansible_become_pass=[sudo user password]'
```
