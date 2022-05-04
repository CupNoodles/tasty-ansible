Role Name
=========

Ansible role for bootstrapping a webserer with TastyIgniter installed. 

Role Variables
--------------

The following variables must be set per host in order to use this role (unless it's a vagrant host). 

```

```

### Deplpoy user and public key path

This ansible role creates a new user (called 'deploy' by default) for `ssh`ing into your server. The user is in the web user (`www-data` by default) group, in order to avoid permissions issues when updating TI plugins through a mix of command-line and web UI. This may not be everybody's preference, and can be disabled entirely with the `create_deploy_user` flag if you wish. 

If you do use the setup as-is, it's highly convenient to enable agent forwarding and include your public key path in the above variables. This way, for instance, you can easily clone your own private Github repos straight into a development servers `extensions/` directory. This means that for Vagrant development boxes, you should ssh into your VM as the deploy user and not the default vagrant user - for example, `ssh -p2220 deploy@127.0.0.1` as opposed to `vagrant ssh`. 


Usage
-----

This repo is intended for use with the tasty-vagrant and tasty-deploy repo's respectively. Please refer to the code in those repositories for usage examples. 

Updates/Contributing
-------

PRs are welcome! 

