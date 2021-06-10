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

```
sudo ansible-pull -U https://github.com/lyssar/ansible-workstations.git
```