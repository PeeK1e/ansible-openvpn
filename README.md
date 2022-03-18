## Ansible Openvpn Playbook
This repository contains an Ansible Playbook to install OpenVPN on an Debian system.

### Installing
If you want to install the VPN modify the `inventory` file to fit your target machine IP, User and SSH Port.

*Hint: Add your SSH user to the sudoers file and make sure that the user can execute all commands without password*

Place your SSH key on the target machine beforehand.
If you want to modify any settings rename the `group_vars.custom` folder to `group_vars` and set, but don't remove, any variables according to your needs.

After this you may execute the following command
```
ansible-playbook -i inventory --private-key=/path/to/your/sshkey type_full_install.yaml
```

### Adding Clients
If you have specified any clients in the `group_vars/all/global.yaml` they will be automatically created if you install for the first time.

If you already installed the system, just add any clients you want to create into the list and execute the playbook `type_create_client.yaml`

### Removing Clients
#### TO-DO