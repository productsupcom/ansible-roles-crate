# Crate Ansible Roles

## How to Use
There are two roles `crate` and `crate-proxy`.
`crate` simply installs Crate and it's ready to go. However make sure to create a Group in Ansible for all nodes that needs to be available in the Cluster.

`crate-proxy` installs a HaProxy and configures IPTables to drop all non-authenticated traffic to Crate's HTTP port. This will be exposed via HaProxy with HTTP Basic Auth.

Be sure to have your own IPTable rules in place for your other things as this one will just append to your current one ;)

## Groups

```
# ansible_hosts
[crate]
1.2.3.4
1.2.3.5
1.2.3.6
1.2.3.7
```

## Running

Then simply run

```
ansible-playbook -l crate crate.yml
```


Enjoy!

## Warning
Use these roles at your OWN RISK. We are not responsible if because of these Ansible playbooks your cat catches fire or your servers suddenly go missing.

## License
WTFPL see LICENSE
