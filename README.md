## Ansible playbook to run XWCTk installation

### Purpose
[Ansible](https://docs.ansible.com/ansible/latest/getting_started/introduction.html) playbook to provision remote hosts for XWCTk and then install the [XWCTk](https://github.com/uasal/XWCToolkit) & [ESCapps](https://github.com/uasal/ESCapps/) repos.

Ansible does not need to be installed on the remote hosts, just on the <i>control node</i> running the playbook (see requirements.txt). A list of the remote hosts on which to run and the corresponding usernames is provided in `inventory.yml`. The playbook is run on a <i>control node</i> and ansible connects to each remote host and executes the tasks in the playbook.

### How to run
- Create a python environment and install the dependencies in requirements.txt
- Update `inventory.yml` with the target remote host and the corresponding username
- Run the playbook with
```
ansible-playbook -i inventory.yml playbook.yml -K
```
The `-K` means that you will be prompted for the user's sudo password needed to run some of the tasks.

### TODO
- Spin out the .conf files into their own repository
- Add GitHub Action to periodically run playbook and test
