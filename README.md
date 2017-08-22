# raspberry-pi
Raspberry Pi provisioning with:
- [Homebridge](https://github.com/nfarina/homebridge)
- [Xiaomi Mi Home Plugin for Homebridge](https://github.com/Bluebie/homebridge-miio)

## Instructions

### Boot Raspberry Pi
1. Burn [Raspbian Lite](https://www.raspberrypi.org/downloads/raspbian/) with [Etcher](https://etcher.io/) on SD card.
2. Reinsert SD card, and create empty file (`touch ssh`) in `boot` partition on SD card.
3. Insert SD card in Raspberry Pi, connect network cable, and power.
4. Find Raspberry Pi IP address.

### Provision with Ansible
1. Install Ansible on your macOS
```shell
brew install ansible
```
2. Play Ansible playbook
```shell
ansible-playbook --ask-pass -i <ip_address> raspberry-pi.yml
```

## Testing
```shell
vagrant up --no-provision
vagrant provision
```
