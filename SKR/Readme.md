# Commands
https://www.devopsschool.com/blog/ansible-adhoc-commands-lab-excercise-part-1/

- ansible localhost -m group -a "name=deploy"
- ansible localhost -m user -a 'name=deploy-user group=deploy shell="/bin/bash"'
