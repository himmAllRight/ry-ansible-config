# Ryan's Ansible Configuration

This is a set of playbooks and roles to automatically configure my systems. The
roles define the tasks for doing basic things like user setup and package
management. Specifics are supplied to the roles through variables, which are
normally defined in each playbook. This allows each system to easily be defined
and edited by swapping what is in the playbook.

The ultimate goal, is to eventually have a system I can use to completely
configure all of my systems automatically. This should make reformatting my
computers, as well as quickly spinning up VMs/Containers easy.

## Pre Reqs

Right now, there are a few pre-reqs that must be completed before being able to
run the playbooks.

- Ansible Installed (also python installed)
- `python3-devel` installed?
- User needs sudo privileges without password
- Localhost ssh-keys configured (I think?)

*I think that's all. I'll update this next time I spin up a fresh test system.

## Playbook Variables
The specifics for roles are set using variables defined in each playbook. Here
are the available variables that can be used.

### Packages
The package variables define what packages will be installed, using several
types of package managers.

| Variable | Description | Required Role |
|----------|-------------|---------------|
| dnf_add_list | A list of packages to add using the `dnf` package manager | `system/packages/dnf` |
| dnf_remove_list | A list of packages to remove using the `dnf` package manager | `system/packages/dnf` |
| rpmostree_add_list | A list of packages to add using `rpmostree` | `system/packages/rpm-ostree` |
| rpmostree_remove_list | A list of packages to remove using `rpmostree` | `system/packages/rpm-ostree` |
| flathub_install_list | A list of flatpaks to install from flathub | `system/packages/flathub` |


## Examples


## Future Feature Plans

