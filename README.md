TastyIgniter Ansible
=========

Ansible role for bootstrapping a webserer with TastyIgniter installed. 

Host Variables
--------------

More or less every variable in `defaults/main.yml` should be overridden (or at least looked at) for each individual host that this role will be deployed against, unless you're only only creating a vagrant VM.

### Deploy user and public key path

This ansible role creates a new user (called 'deploy' by default) for `ssh`ing into your server. The user is in the web user (`www-data` by default) group, in order to avoid permissions issues when updating TI plugins through a mix of command-line and web UI. This may not be everybody's preference, and can be disabled entirely with the `create_deploy_user`. 

If you do use the setup as-is, it's highly convenient to enable agent forwarding and include your public key path in the above variables. This way, for instance, you can easily clone your own private Github repos straight into a development servers `extensions/` directory. This means that for Vagrant development boxes, you should ssh into your VM as the deploy user and not the default vagrant user - for example, `ssh -p2220 deploy@127.0.0.1` as opposed to `vagrant ssh`. 

Usage
-----

This repo is intended for use with the tasty-vagrant repository. Please refer to https://github.com/CupNoodles/tasty-vagrant for a quick usage example.


