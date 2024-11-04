# Ansible Role: pivpn

An Ansible role that deploys and configures [PiVPN][01] on Linux boxes.

## 🚀 Motivation

I wanted to deploy a self-managed VPN service. [PiVPN][01] is a great alternative for this use case as it supports both [WireGuard](https://www.wireguard.com/) and [OpenVPN](https://openvpn.net/) and differently from what the name of the project suggests, [PiVPN][01] is not meant *only* for [Raspberry Pi](https://www.raspberrypi.com/) based environments.

## 📑 Role Variables

Check `defaults/main.yml`.

## 🧰 Dependencies

None.

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Deploy PiVPN
  hosts: all
  become: true
  gather_facts: true
  vars:
    vpn_endpoint: vpn.example.com
    dns_servers: [ 1.1.1.1, 8.8.8.8 ]
    pivpn_installation_user: admin
    deploy_wireguard: true
    wireguard_port: 123
  roles:
    - fernandobohrer.pivpn
```

## 📋 Usage

Please refer to the documentation available [here](https://docs.pivpn.io/wireguard/) for `WireGuard` and [here](https://docs.pivpn.io/openvpn/) for `OpenVPN` to get the details of how to use [PiVPN][01].

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][02] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][03].

[01]: https://www.pivpn.io/
[02]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[03]: /LICENSE
