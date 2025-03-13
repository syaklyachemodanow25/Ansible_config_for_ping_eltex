# Ansible_config_for_ping_eltex
apt-get install ansible sshpass
Уберите проверку публичного ssh ключа ansible, для этого раскомментируйте в файле /etc/ansible/ansible.cfg строку: //обязательно везде на машинах включите ssdd

host_key_checking = False

 /etc/ansible/hosts

 all:
  vars:
    ansible_python_interpreter: /usr/bin/python3

LNX:
  hosts:
    SRV:
      ansible_host: ypu_ip
      ansible_user: sshuser
      ansible_port: you_port
    CLI:
      ansible_host: you_ip
      ansible_user: user
  vars:
    ansible_password: you_passwd

RTR:
  hosts:
    HQ-RTR:
      ansible_host: you_ip
      ansible_user: net_admin
    BR-RTR:
      ansible_host: you_ip
      ansible_user: net_admin
  vars:
    ansible_connection: network_cli
    ansible_network_os: ios
    ansible_password: you_passwd

ansible all -m ping
