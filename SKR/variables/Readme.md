# Variables
https://www.devopsschool.com/tutorial/ansible/variables/index.html

- ansible-playbook -i inventory web.yaml -u vagrant --private-key=../login.pem -b
- ansible-playbook -i inventory web_external_vars.yaml -u vagrant --private-key=../login.pem -b
- ansible-playbook -i inventory_vars web_inventory_vars.yaml -u vagrant --private-key=../login.pem -b
