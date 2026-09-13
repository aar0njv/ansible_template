# Steps

- Make host key checking false
  ```
  vim /etc/ansible/ansible.cfg
  ```
  [defaults]
  host_key_checking = False

- Run the playbook
  ```
  ansible-playbook -i web-inventory tcpudp-ports.yml --ask-pass -b -K -vv
  ```
  - `-i <inv-file-name` target inventory file
  - `--ask-pass` Prompts you for the SSH password of the target machine
  - `-b` Enables *become*, allows Ansible to execute tasks with elevated privileges (sudo)
  - `-K` Prompts for the become password
  - `-vv` for troubleshooting, displays logs
