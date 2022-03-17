## Ansible Openvpn Playbook
This repository contains an Ansible Playbook to install OpenVPN on an Debian system.

### Installing
If you want to install the VPN modify the `inventory` file to fit your target machine IP, User and SSH Port.

*Hint: Add your SSH user to the sudoers file and make sure that the user can execute all commands without password*

Place your SSH key on the target machine beforehand.
If you want to modify any settings rename the `group_vars.custom` folder to `group_vars` and set or remove any variables to according your needs.

***You may need to execute the `type_prepare_host.yaml` if your target machine doesn't have `python3` yet***

After this you may execute the following command
```
ansible-playbook -i inventory --private-key=/path/to/your/sshkey type_full_install.yaml
```
