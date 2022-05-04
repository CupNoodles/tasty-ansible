Role Name
=========

Ansible role for bootstrapping a webserer with TastyIgniter installed. 

Role Variables
--------------

The following variables must be set per host in order to use this role (unless it's a vagrant host). 

```

```

### Deplpoy user and public key path

This ansible role creates a new user (called 'deploy' by default) for `ssh`ing into your server. The user is in the web user (`www-data` by default) group, in order to avoid permissions issues when updating TI plugins through a mix of command-line and web UI. This may not be everybody's preference, and can be disabled entirely if you wish. 

If you do use the setup as-is, it's highly convenient to enable agent forwarding and include your public key path in the above variables. This way, for instance, you can easily clone your own private Github repos straight into a development servers `extensions/` directory. This means that for Vagrant development boxes, you should ssh into your VM as the deploy user, for example `ssh -p2220 deploy@127.0.0.1` as opposed to using vagrant's own user, or the `vagrant ssh` command. 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD


