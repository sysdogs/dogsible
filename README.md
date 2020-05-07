# dogsible

## Python virtual environment creation

First install virtualenv:
```
sudo pip install virtualenv
```
- Create a virtual environment
```
virtualenv < new virtual environment name >
```
- Or, if using Python3, create virtualenv like this instead
```
virtualenv -p python3 myenv
OR
python3 -m venv myenv
```
- Activate your virtual environment
```
source < new virtual environment name >/bin/activate
```
- Install requirements from requirements.txt (Including pre-commit)
```
sudo pip install -r requirements.txt
```
## pre-commit installation on MacBook using Homebrew
```
brew install pre-commit
```
### Non-administrative installation:

```
curl https://pre-commit.com/install-local.py | python
```
- to upgrade: run again, to uninstall: pass `uninstall` to Python

- does not work on platforms without symlink support (Windows)
### Requirements addition

Add
```
< your new requirement >
```
to requirements.txt or requirements-dev.txt

## Vagrant node setup
### 1. Install VirtualBox
 Debian:
 ```
 apt-get install virtualbox-"version"
 ```
 CentOS
 ```
 sudo yum install virtualbox
 ```
 Homebrew (MacBook)
 ```
 $ brew cask install virtualbox
 ```
### 2. Install Vagrant

Debian
```
curl https://releases.hashicorp.com/vagrant/2.2.7/vagrant_2.2.7_x86_64.deb

sudo apt install ./vagrant_2.2.7_x86_64.deb
```

CentOS
```
sudo wget https://releases.hashicorp.com/vagrant/2.2.7/vagrant_2.2.7_x86_64.rpm

sudo yum -y localinstall vagrant_2.2.7_x86_64.rpm
```
Homebrew (MacBook)
```
brew cask install vagrant
```
### 3. Install Ansible

Debian
```
sudo apt install ansible
```
CentOS
```
sudo yum install ansible
```
Homebrew (MacBook)
```
brew install ansible
```
### 4. Run Vagrant up and provision your virtual machine
```
/inventories/0-tests/vagrant vagrant up <selected machine inventory name/s>
```
After Vagrant installation:
 - The basic configuration settings(Name/IP Address/RAM/VCPU) can be found in `/inventories/0-tests/vagrant/Vagrantfile.servers.yml` file.

 - The group configuration can be found in the Vagrantfile - `/inventories/0-tests/vagrant/Vagrantfile.yml`

 - Setting group variables can be done by creating group variable files in `/inventories/0-tests/vagrant/.vagrant/provisioners/ansible/inventory/group_vars` directory
## Naming conventions and other contribution guidelines
If you want to contribute, please see:
[contribution.md](contribution.md)
