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
- ansible localhost -m git -a 'repo="https://github.com/devopsschool-lab-exercise/tesco-git-ansible-nov-2019.git" dest="/tmp/test" '
- ansible localhost -m file -a 'path="/opt/test.txt" state=touch'
- ansible localhost -m file -a 'path="/opt/test.txt" state=absent'
- ansible localhost -m reboot # Cannot kill yourself.


## Remote server
- ansible all -i 172.42.42.102, -m yum -a 'name=wget' -u vagrant --private-key login.pem -b
- [root@centosvm01 ~]# ansible all -i 172.42.42.102, -m reboot -u vagrant --private-key login.pem -b
172.42.42.102 | CHANGED => {
    "changed": true,
    "elapsed": 19,
    "rebooted": true
}


- ansible all -i inventory -m yum -a "name=wget state=installed" -u vagrant --private-key login.pem -b
- ansible gog -i inventory1 -m yum -a "name=wget state=installed" -u vagrant --private-key login.pem -b
- ansible-playbook -i inventory1 web.yaml -u vagrant --private-key=login.pem -b
