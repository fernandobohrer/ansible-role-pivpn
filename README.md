# Ansible Role: pivpn

An Ansible role that deploys and configures [PiVPN][01] on Linux boxes.

## 🚀 Motivation

I wanted to deploy a self-managed VPN service. [PiVPN][01] is a great alternative for this use case as it supports both [WireGuard][02] and [OpenVPN][03] and differently from what the name of the project suggests, [PiVPN][01] is not meant *only* for [Raspberry Pi][04] based environments.

## 📑 Role Variables

Check [here][05].

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
    pivpn__vpn_endpoint: vpn.example.com
    pivpn__dns_servers: [1.1.1.1, 8.8.8.8]
    pivpn__deployment_user: admin
    pivpn__deploy_wgrd: true
    pivpn__wgrd_port: 123
  roles:
    - fernandobohrer.pivpn
```

## 📋 Usage

Please refer to the documentation available [here][06] for `WireGuard` and [here][07] for `OpenVPN` to get the details of how to use [PiVPN][01].

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][08] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][09].

[01]: https://www.pivpn.io/
[02]: https://www.wireguard.com/
[03]: https://openvpn.net/
[04]: https://www.raspberrypi.com/
[05]: defaults/main.yml
[06]: https://docs.pivpn.io/wireguard/
[07]: https://docs.pivpn.io/openvpn/
[08]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[09]: /LICENSE
