# Ansible Role: watchtower

An Ansible role that deploys [watchtower][01] to keep your containerized workloads up-to-date automatically.

## 🚀 Motivation

From watchtower's [GitHub repository][01]:

*With watchtower you can update the running version of your containerized app simply by pushing a new image to Docker Hub or your own image registry.*

*Watchtower will pull down your new image, gracefully shut down your existing container and restart it with the same options that were used when it was deployed initially.*

This role deploys [watchtower][01] and its dependencies and configures the solution to keep your containerized workloads up-to-date automatically.

## 📑 Role Variables

Check `defaults/main.yml`.

## 🧰 Dependencies

Check `meta/main.yml`.

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Deploy watchtower
  hosts: all
  become: true
  gather_facts: true
  roles:
    - fernandobohrer.watchtower
```

## 📋 Usage

From watchtower's [documentation][02]:

*By default, watchtower will watch all containers. However, sometimes only some containers should be updated.*

If you need to exclude some containers from the update process, set the `com.centurylinklabs.watchtower.enable` label to `false` on the container you want to remove from the update process.

For clarity, this should be set on the containers you wish to be ignored from the update process. This is *not set* on the watchtower container itself. For more details, please check [here][03].

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][04] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][05].

[01]: https://github.com/containrrr/watchtower
[02]: https://containrrr.dev/watchtower/container-selection/
[03]: https://containrrr.dev/watchtower/container-selection/#full_exclude
[04]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[05]: /LICENSE
