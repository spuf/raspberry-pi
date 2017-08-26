# raspberry-pi
Raspberry Pi provisioning with:
- [Homebridge](https://github.com/nfarina/homebridge)
- [Xiaomi Mi Home Plugin for Homebridge](https://github.com/Bluebie/homebridge-miio)

## Setup

### Boot Raspberry Pi
1. Write [Raspbian Lite](https://www.raspberrypi.org/downloads/raspbian/) with [Etcher](https://etcher.io/) on SD card.
2. Remount SD card, and create an empty file named `ssh` in `boot` partition on SD card.
3. Insert SD card in Raspberry Pi, connect network cable, and power.
4. Find Raspberry Pi IP address.

### Provision with Ansible
1. [Install Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html) on your macOS
```shell
sudo -H pip install --ignore-installed --upgrade ansible
```
2. Play Ansible playbook for first time, replace `192.168.1.23` with Raspberry Pi IP address:
```shell
ANSIBLE_HOST_KEY_CHECKING=0 ansible-playbook -i inventory.ini -e 'ansible_host=192.168.1.23 ansible_ssh_pass=raspberry' raspberry-pi.yml
```
3. Try to connect to Raspberry Pi: 
```shell
ssh pi@pi.local
```
4. Play Ansible playbook for update:
```shell
ansible-playbook -i inventory.ini raspberry-pi.yml
```

## Testing
```shell
vagrant up --no-provision
vagrant provision
```
