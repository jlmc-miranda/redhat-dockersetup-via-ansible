# Docker Installation


## AWS Red Hat
```
# show all available repos
yum repolist all

yum-config-manager --enable rhui-REGION-rhel-server-extras
yum-config-manager --enable epel
```


## Pre-Steps

### Proxy Configuration

If you're behind a proxy, export these variables:
```
# set proxy
export http_proxy=http://<proxy_server>:<proxy_port>
export https_proxy=${http_proxy}
```

This will work for `pip` and `git`.


### Git Installation
Install `git` to clone this repo.
```
yum install git
git clone https://github.com/pstauffer/redhat-dockersetup-via-ansible.git
```

### Ansible Installation

#### via yum

```
# get epel repo, needed for ansible rpm
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

# install ansible
yum install ansible
```


#### via pip

```
# get epel repo, needed for python-pip rpm
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

# install pip and gcc
yum install python-pip gcc

# install ansible
pip install ansible
```

## Run Ansible Playbook
```
ansible-playbook install.yml
```
