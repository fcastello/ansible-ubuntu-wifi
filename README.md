ansible-ubutu-wifi
=========

This role is intended to install wifi in an ubuntu server using netplan. I will try not to conflict with other configurations, it will only add wifi configuration

Requirements
------------

- Ubuntu 18.04 or newer (was tested with 18.04)

Role Variables
--------------
Check `defaults/main.yml` to know the varaibales defaults

```yaml
# Wifi interface
ansible_netplan_wifi_if: wlan0
# SSID of wireless network
ansible_netplan_wifi_ssid: my-wifi
# Beware that running it in this the password might be disclosed to public, 
# it's up to the person implementing the playbook to keep the password secure
# I suggest to set this variables in an ansible vault files, or asking for the password interactively using ansible prompts. 
# Never store the password in plain text
ansible_netplan_wifi_password: mySecurePassword
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: fcastello.ubuntu_wifi, ansible_netplan_wifi_ssid: 'myssid', ansible_netplan_wifi_password: "supersecretpassword"}

Limitations
-----------

- This is limited to configure just 1 wifi interface
- It was tested on ubuntu 18.04 runnong on raspberry pi 3/4. howevers it should work for any ubuntu18.04 as it is usiong standard ubuntu packages

License
-------

MIT

Disclaimer
----------

This project was to automate installation of a raspberry pi cluster in a home DIY project, it is far from being production ready and doesn't configure all features of wifi nor netwplan. Use at your own risk
