# Ryan's Ansible Configuration

This is a set of playbooks and roles to automatically configure my systems. The
plan is to have several "base" profiles to configure various systems, and then
roles for each of my "application" or project configurations that I can layer
on top.

The ultimate goal, is to eventually have a system I can use to completely
configure all of my systems automatically. This should make reformatting my
computers, as well as quickly spinning up VMs/Containers easy.

*Note: For now, the stuff is somewhat hard coded for me and my username/desired
install locations. Once I have the frame setup, I plan to abstract out some of
the hard-code stuff and have it defined with a config file.*

## Pre Reqs

Right now, there are a few pre-reqs that must be completed before being able to
run the playbooks.

- Ansible Installed (also python installed)
- `/etc/ansible/hosts` configured
- User needs sudo privileges without password
- Localhost ssh-keys configured (I think?)

*I think that's all. I'll update this next time I spin up a fresh test system.

## Examples

Setup my Fedora workstations (note, this is mostly for me still. It will pull
down my other Github repos and stuff :P ).

```
ansible-playbook playbooks/fedora-workstation.yml
ansible-playbook playbooks/configure-gnome.yml
```

## Future Feature Plans

- Roles
  - Systems
    - System Bases
      - [X] Fedora Workstation
      - [X] Fedora SilverBlue
      - [ ] Fedora Cloud
      - [ ] CentOS Server?
      - [ ] Ubuntu Server?
      - [ ] Ubuntu Cloud
    - Desktop Environments
      - [ ] Gnome
        - [X] Download/Set Theme
        - [X] Download/Set Icons
        - [ ] Gnome Tweaks Switches
          - [ ] Enable Gnome Extensions (if tweaks installed?)
            - [ ] Enable User Shell Themes/Switch theme
            - [ ] Install Topicons Plus
            - [ ] Sound input & output device chooser
            - [ ] Media Player indicator
            - [ ] ... other?
          - [ ] Caps to CTRL
          - [ ] Turn on Battery Percentage in Top Bar
          - [ ] Turn on Date in Top Bar
          - [ ] Switch on Minimize and Maximize buttons
        - [ ] Set Keyboard shortcuts
      - [ ] Plasma
        - [ ] Download/Switch Theme
        - [ ] Download/Switch Icons
        - [ ] Switch Keyboard commands
        - [ ] Add keyboard launch commands for passmenu and terminal
      - [ ] Mate
        - [ ] Download/Switch Theme
        - [ ] Download/Switch Icons
        - [ ] Switch Keyboard commands
        - [ ] Add keyboard launch commands for passmenu and terminal
  - Apps
    - [X] Dotfiles
    - [X] ry-org-scrum
    - [X] scripts
    - [X] Website
    - [ ] Pass
    - [ ] ssh
      - [ ] Add keys to Github? (after config added)
      - [ ] Add other ssh keys
      - [ ] Configure yubikey access
    - [ ] ...More to add...
  - Role Improvements
    - [ ] Add configuration settings
    - [ ] Swap out hard-coded user
    - [ ] Conditionalize options with tag/flags