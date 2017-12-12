Stouts.hostname
===============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.hostname.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.hostname)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.hostname-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/845)

Ansible role for manage the hostname

#### Variables

The role variables and default values.

```yaml
hostname_enabled: yes                       # Enable module
hostname_hostname: "{{inventory_hostname}}" # Set hostname
hostname_hostname_short: "{{hostname_hostname.split('.')[:-1]|join('.')}}" # Set short hostname
```

#### Requirements

If /etc/hostname has *not* already been created by the installer
(e.g. a debootstrap system), AND you have already set an unusually
restrictive umask, then /etc/hostname could be created with
unusually restrictive permissions.  Try not to do that.

This would probably only cause obscure, unusual (difficult to troubleshoot :)
problems.  /etc/hostname is only expected to be used by privileged software
at boot time.  Most other software should query the kernel value which the
boot software set up, i.e. gethostname().

This is a limitation in the Ansible hostname module (as of v2.3.1).
It does not enforce standard permissions for /etc/hostname.
We don't try to set permissions ourself because some distributions use
a different config file than /etc/hostname.

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.hostname/issues)!
