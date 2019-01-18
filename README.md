# pihole-ansible

Setup your Raspberry Pi as Pi-Hole DNS server.

## Requirements

- Flash a **clean** Raspbian Lite image on an SD card
  URL: https://www.raspberrypi.org/downloads/raspbian/
- Enable SSH on the Raspberry (it is disabled by default). You can:
    - use `raspi-config` to enable SSH
    - create a file `/boot/ssh`
- Find the IP address your router will give to the Raspberry Pi
- You need Ansible installed on your local computer (not the Raspberry Pi)

## Installation

On your local computer, clone and setup this ansible playbook.

```
git clone https://github.com/maxbachmann/pihole-ansible.git
cd pihole-ansible
cp hosts.example hosts
```

Edit the `hosts` file and set the IP address of your RPI.

Deploy using [ansible](http://www.ansible.com) (install instructions for ansible are in [requirements](#requirements) below).

```
./playbook.yml
```

Or:
```
ansible-playbook playbook.yml -i hosts --ask-pass --become -c paramiko
```
