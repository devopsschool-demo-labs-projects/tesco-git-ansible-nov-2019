# Commands
https://www.devopsschool.com/blog/ansible-adhoc-commands-lab-excercise-part-1/

- ansible localhost -m group -a "name=deploy"
- ansible localhost -m user -a 'name=deploy-user group=deploy shell="/bin/bash"'
- ansible localhost -m yum -a 'name=httpd state=installed'
- ansible localhost -m service -a 'name=httpd state=started enabled=yes'
- ansible localhost -m file -a 'path="/var/www/html/index.html" state=touch'
- ansible localhost -m blockinfile -a 'create=yes path=/var/www/html/index.html block="Hello World"'
- ansible localhost -m copy -a 'src="/var/www/html/index.html" dest="/var/www/html/second.html" '
- ansible localhost -m yum -a "name=git,wget state=installed"
