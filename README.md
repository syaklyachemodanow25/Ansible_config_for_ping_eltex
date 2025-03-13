![image](https://github.com/user-attachments/assets/c3f71cf0-5a69-4f82-a22f-fbb1876cd933)# Ansible_config_for_ping_eltex
apt-get install ansible sshpass
Уберите проверку публичного ssh ключа ansible, для этого раскомментируйте в файле /etc/ansible/ansible.cfg строку: //обязательно везде на машинах включите ssdd

host_key_checking = False

 /etc/ansible/hosts

![image](https://github.com/user-attachments/assets/3804b500-19be-4409-9cdc-fd6da63f986c)


ansible all -m ping
