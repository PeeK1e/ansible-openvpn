## Ansible Openvpn Playbook
This repository contains an Ansible Playbook to install OpenVPN on an Debian system.

It only supports IPv4 for the moment.

### Installing

***Place your SSH key on the target machine beforehand.***

*Hint: Add your SSH user to the sudoers file and make sure that the user can execute all commands without password*

If you want to install the VPN copy the `inventory.testing` file to `inventory` and modify it to fit your target machine IP, User and SSH Port.

Copy the `group_vars.custom` folder to `group_vars` and modify, but don't remove, any variables according to your needs.

After this you may execute the following command
```
ansible-playbook -i inventory --private-key=/path/to/your/sshkey type_full_install.yaml
```

### Adding Clients
If you have specified any clients in the `group_vars/all/global.yaml` they will be automatically created if you install for the first time.

If you already have installed the system and just want to add clients, remove any clients from the list in the `group_vars/all/global.yaml`, add the new clients to the list and execute the playbook `type_create_client.yaml`

#### TO-DO Skip already existing clients

### Removing Clients
#### TO-DO