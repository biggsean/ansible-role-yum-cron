Role Name yum-cron
=========

Install and configure yum-cron on Centos 6/7

This installs yum-cron to it's defaults unless they are overridden.  Keep in mind that CentOS6 it is default to install updates where in CentOS7 it is not.  You may consider creating a dynamic group that configures these as appropriate.

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

### yumcron_update_cmd
#### CentOS 7
Default: *default*

This sets the update_cmd parameter for yum-conf.

#### CentOS 6
Default: *""*

This corresponds to the YUM_PARAMETER Option.
### yumcron_apply_updates
#### CentOS 7
Default: *no*

Have yum-cron apply the updates.
#### CentOS 6
Default: *yes*

This toggles DOWNLOAD_ONLY.  (yumcron_apply_updates = yes will set DOWNLOUD_ONLY to "no" and vice versa)
### yumcron_emit_via (CentOS 7 only)
Default: *stdio* if yumcron_email_to is _not_ defined else *email*
You can also set this to the value you like.  In this case, it will set to your value and not depend on yumcron_email_to.

### yumcron_email_to
#### CentOS 7
Default: *root*
#### CentOS 6
Default: *""*

Dependencies
------------

None

Example Playbook
----------------


    - hosts: servers
      roles:
         - { role: biggsean.yum-cron, yumcron_email_to: someone@example.com }

License
-------

MIT

