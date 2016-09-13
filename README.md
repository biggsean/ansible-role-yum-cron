Role Name yum-cron
=========
[![Build Status](https://travis-ci.org/biggsean/ansible-role-yum-cron.svg?branch=master)](https://travis-ci.org/biggsean/ansible-role-yum-cron)
Install and configure yum-cron on Centos 6/7

Requirements
------------

None

Role Variables
--------------

### yumcron_update_on_ansible_run
Default: *false*
When set to true the role will run a yum update every time.

### yumcron_update_on_first_run
Default: *true*
This will check to see if yum-cron is installed and bring the machine up to date if it has not been installed yet.  This is beneficial if you start with this role that the machine will updated on the first provision.

### yumcron_update_cmd (CentOS 7)
Default: *default*
This sets the update_cmd parameter for yum-conf.

### yumcron_apply_updates (CentOS 7)
Default: *"no"* (quotes are required)
Have yum-cron apply the updates.

### yumcron_emit_via (CentOS 7)
Default: *stdio* if yumcron_email_to is _not_ defined else *email*
You can also set this to the value you like.  In this case, it will set to your value and not depend on yumcron_email_to.

### yumcron_email_to (CentOS 7)
Default: *root*


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
