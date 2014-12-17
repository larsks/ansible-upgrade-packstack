These playbooks will upgrade a packstack-deployed OpenStack deployment
from Icehouse to Juno.  They have been tested against [RHEL OSP][] 5 on
[RHEL][] 7.

[rhel osp]: http://www.redhat.com/en/technologies/linux-platforms/openstack-platform
[rhel]: http://www.redhat.com/en/technologies/linux-platforms/enterprise-linux

## Getting started

1. Copy your packstack answers file into this directory as `answers.txt`.
1. Run `ansible-playbook`:

        ansible-playbook playbook.yml

1. Go out for a coffee or something.

When you come back, you should have a functional (*) Juno deployment.

(*) Functional except for bz [1175502][].

[1175502]: https://bugzilla.redhat.com/show_bug.cgi?id=1175502

