# Debian workstation setup

## Install ansible

### For Linux

```bash
sudo apt-get install -y python3-pip python3-setuptools python3-wheel
sudo pip3 install --prefix /usr/local ansible
```

#### For development install ansible lint

```bash
sudo pip3 install --prefix /usr/local ansible-lint
```

## How to use

### Linux 
```
# example for changing configuration, you have todo this for at least your zsh user.
VAR_CHANGES=$(cat /path/to/you/overwrite_vars.json);

ansible-pull -K -U https://github.com/lyssar/ansible-workstations.git \
    -e '${VAR_CHANGES}' \
    debian/main.yml
```

#### Notes
> **Do not** sudo ansible-pull unless you want to create all stuff as `root`. For root execution you will get asked for the become password so all applications can be installed without sudoing the pull command.

> If you want to change configurations like workspace folders or zsh user you have to use the .json format for -e|--extra-vars like above. To now which conigurations exist please look into [vars/main.yml](./vars/main.yml)
