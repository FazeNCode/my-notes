
<h3> What is Ansible? </h3>
Ansible is an open source, command line interface automation tool.
Automate service installs 
Advance workflow (patching systems)
Agentless
Configure Systems / Install packages / Install services 
Written in Python




<h3> Ansible Core Components: </h3>

<h4> Control Node: </h4>
Responsible for managing and orchestrating the automation tasks
Write and execute Ansible playbook, manage inventory files
Communicate with managed nodes

<h4> Managed Node: </h4>

<h4> Inventory: </h4>
List of managed nodes that Ansible will work with
Defines the hosts and groups of hosts which Ansibile will target
Can be statics (manually configure) or dynamic by scripts or plugins
Define variables and group information in the inventory file
The path to inventory file by default is  “/etc/ansible/hosts”

<h4> Playbooks: </h4>
List of managed nodes that Ansible will work with
Referred to as a script, written in yaml (yet another mark-up language)
Defines the hosts and groups of hosts which Ansibile will target
Can be statics (manually configure) or dynamic by scripts or plugins
Define variables and group information in the inventory file

<h4> Roles: </h4>
Organize and package playbook and variables and task into reusable components
Structured way to manage the automation of specific functions or services

<h4> Modules: </h4>
Modules are small, standalone scripts that Ansible uses to perform specific tasks on managed nodes.
built-in modules for tasks like package management, file manipulation, and service control.
can also write custom modules if needed.


Facts:
gathers information about managed nodes such as their hostname, IP address, hardware details
facts can be used in playbooks to make automation tasks more dynamic and adaptable.

Handlers:
Are special tasks in Ansible playbooks that are only executed when notified by other tasks
Typically used to restart services or perform other actions in response to changes made by playbooks.


