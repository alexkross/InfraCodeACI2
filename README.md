# InfraCodeACI2

This is an example implementation for Infrastructure as Code for Cisco ACI and dockerized computing resources on Ansible Host on VMware ESXi v6.5 host under vCenter. This project uses Ansible and GitLab CI/CD for complete automation.

Consider these Ansible playbooks as a template/skeleton/sample that need customization for your particular environment and requirements.

InfraCodeACI1 project is another example with linux bare-metal external computing resources.

## Prerequisites

- Working Cisco ACI fabric.
- Account granted an admin role.
- VMware vCenter v6 or higher.
- CentOS or RedHat Atomic Host VM with an NIC mannually bound to provided MAC for management.
- Vault`ed passwords placed in host_vars/.
- Ansible configuraion supposedly in $HOME/.ansible.cfg.
- Ansible inventory supposedly in $HOME/.ansible.hosts with appropriate options and group definitions.
- Working GitLab installation with shell runner configured, tagged for ansible, registered, enabled/started and assinged to the project.
- Reflected ansible environment into gitlab-runner home directory (/var/lib/gitlab-runner/ in my case). Proper permissions must be set.

## Topology

Pretty trivial for the sake of cloning and reusing:

- Single APP of single EPG.
- Single VRF and BD that will be extended to an external L2out.
- One L2 external domain and access policies cofigured in the ACI fabric.
- Contract allowing communication b/w EPGs is common/default.
