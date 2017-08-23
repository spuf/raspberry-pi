# raspberry-pi
Raspberry Pi provisioning with:
- [Homebridge](https://github.com/nfarina/homebridge)
- [Xiaomi Mi Home Plugin for Homebridge](https://github.com/Bluebie/homebridge-miio)

## Setup

### Boot Raspberry Pi
1. Burn [Raspbian Lite](https://www.raspberrypi.org/downloads/raspbian/) with [Etcher](https://etcher.io/) on SD card.
2. Reinsert SD card, and create empty file (`touch ssh`) in `boot` partition on SD card.
3. Insert SD card in Raspberry Pi, connect network cable, and power.
4. Find Raspberry Pi IP address.

### Provision with Ansible
1. [Install Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html) on your macOS
```shell
sudo -H pip install --ignore-installed --upgrade ansible
```
2. Play Ansible playbook for first time, replace `192.168.1.255` with Raspberry Pi IP address:
```shell
ansible-playbook -i inventory.ini -l firstrun -e 'ansible_host=192.168.1.255' raspberry-pi.yml
```
3. Play Ansible playbook for other times:
```shell
ansible-playbook -i inventory.ini -l pi raspberry-pi.yml
```

## Testing
```shell
vagrant up --no-provision
vagrant provision
```
