# Ansible

## ansible-pull

ansible-pull comes with ansible installation. No additional installation is required.

**ansible-pull allows machine's to 'pull' ansible-playbooks from a git server & then run them locally.**

_No need to maintain a central server. So, practically no single point of failure if GitHub is used_

In a general ansible scenario,

![normal ansible scenario](<../../.gitbook/assets/image (2).png>)

Here, ansible server centrally manages 4 machines. If one of the machine is unreachable for some reasons, ansible throws an error. But, what if you want your machine to be offline for a certain period of time? And only want them to run ansible-playbook in your specified time or time gaps?

Here comes ansible-pull

![typical ansible-pull scenario](<../../.gitbook/assets/image (3).png>)

Machines pull ansible-playbook from git server and run them locally, You can create cron jobs for specified users to have better control over ansible.

_I have a_ [_project_](https://github.com/NafiAsib/ansible-dots) _on managing workstations with ansible-pull, do check it out_

### Links

* [Get a variable with host username](https://stackoverflow.com/questions/26394096/how-do-i-get-a-variable-with-the-name-of-the-user-running-ansible)
* [Getting started with Ansible, LearnLinuxTV](https://www.youtube.com/playlist?list=PLT98CRl2KxKEUHie1m24-wkyHpEsa4Y70) - Easy tutorial series
* [Desktop config with Ansible, LearnLinuxTV](https://www.youtube.com/watch?v=gIDywsGBqf4) - Problem to my solution
* [substring in when condition](https://stackoverflow.com/questions/36496911/run-an-ansible-task-only-when-the-variable-contains-a-specific-string)
* [Edit current user's shell with Ansible](https://stackoverflow.com/questions/43560657/edit-current-users-shell-with-ansible)

### Official Doc

* [Playbook variables](https://docs.ansible.com/ansible/latest/user\_guide/playbooks\_variables.html)
* [Git](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/git\_module.html)&#x20;
* [Include task module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/include\_tasks\_module.html)
* [file module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file\_module.html)
* [lookup](https://docs.ansible.com/ansible/latest/plugins/lookup.html)

_**all figures are created by me with**_ [**FigJam**](https://www.figma.com/figjam/)****
