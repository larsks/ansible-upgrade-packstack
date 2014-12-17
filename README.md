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

## Functional testing

These playbooks will run `check_all.yml` between each major component
upgrade to verify that your OpenStack environment is still minimally
functional.  This will run the `openstack-validate` script, which
boots a `cirros` instance and verifies that it becomes `ACTIVE`.

This script does not exercise all OpenStack components, but it
acts as a reasonable canary for a variety of problems.

## Interesting bits

The `packstack-hosts` file included in this directory is an Ansible
[dynamic inventory][] script that reads your Packstack answers file to
determine the hosts involved in your OpenStack deployment.

[dynamic inventory]: http://docs.ansible.com/intro_dynamic_inventory.html

## License

Ansible playbooks for upgrading a Packstack-deployed OpenStack environment  
Copyright (C) 2014 Lars Kellogg-Stedman <lars@oddbit.com>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

