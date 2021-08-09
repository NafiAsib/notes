# Ansible

## ansible-pull

ansible-pull comes with ansible installation. No additional installation is required.

**ansible-pull allows machine's to 'pull' ansible-playbooks from a git server & then run them locally.**

_No need to maintain a central server. So, practically no single point of failure if GitHub is used_

In a general ansible scenario,

![normal ansible scenario](../.gitbook/assets/image%20%282%29.png)

Here, ansible server centrally manages 4 machines. If one of the machine is unreachable for some reasons, ansible throws an error. But, what if you want your machine to be offline for a certain period of time? And only want them to run ansible-playbook in your specified time or time gaps?

Here comes ansible-pull

![typical ansible-pull scenario](../.gitbook/assets/image%20%283%29.png)

Machines pull ansible-playbook from git server and run them locally, You can create cron jobs for specified users to have better control over ansible.

_I have a project on managing workstations with ansible-pull, do check it out_

### Links

* [Get a variable with host username](https://stackoverflow.com/questions/26394096/how-do-i-get-a-variable-with-the-name-of-the-user-running-ansible)
* [Getting started with Ansible, LearnLinuxTV](https://www.youtube.com/playlist?list=PLT98CRl2KxKEUHie1m24-wkyHpEsa4Y70) - Easy tutorial series
* [Desktop config with Ansible, LearnLinuxTV](https://www.youtube.com/watch?v=gIDywsGBqf4) - Problem to my solution
* [substring in when condition](https://stackoverflow.com/questions/36496911/run-an-ansible-task-only-when-the-variable-contains-a-specific-string)
* [Edit current user's shell with Ansible](https://stackoverflow.com/questions/43560657/edit-current-users-shell-with-ansible)

### Official Doc

* [Playbook variables](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html)
* [Git](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/git_module.html) 
* [Include task module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/include_tasks_module.html)
* [file module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html)
* [lookup](https://docs.ansible.com/ansible/latest/plugins/lookup.html)

### Desktop configuration

* [.dots](https://github.com/Addvilz/dots) - dotfiles with ansible
* [Ansible-WSL](https://github.com/Wintus/Ansible-WSL)
* [Setup](https://github.com/jasonwc/setup) - Ansible Playbooks for setting up an ops/ruby/elixir focused workstation
* [Personal Ansible Desktop Configs](https://github.com/LearnLinuxTV/personal_ansible_desktop_configs) - great example of ansible-pull

_**all figures are created by me with**_ [**FigJam**](https://www.figma.com/figjam/)\*\*\*\*

