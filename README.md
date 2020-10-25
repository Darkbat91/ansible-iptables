# Iptables formater for Ansible
Configures an easy to adjust iptables structure with comments that allow a lineinfile or block in file construct to create complex ip table rules

## Defaults
By default the rule sets a DROP for all filter chains and then allows the following rules

- port 22 for ssh access to the world!
- Any connection that is related or established
- all loop back entries
- 


It then drops the following connections

- Any connection with an invalid state
- Forwarding of netbios
- Forwarding of smb

## Usage
Each of the tables have a comment in order to add rules and chains specifically to that table.

for example `#filter_chains` allows you to add a new chain to the filter table and then you can add a rule to that chain after `#filter_rules`.

## Why SSH from everywhere????
This iptables role is configured to allow all ssh access since it is primarily used in my environment to configure cloud servers and the ssh access is controlled at the network access and firewall level that can easily be updated inside of the web portal or with terraform.

Updating iptables inside of those environments is a lot harder without running odd console type commands. 