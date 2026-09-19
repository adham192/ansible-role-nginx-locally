Nginx Locally
=============

An Ansible role to install, configure, and manage Nginx locally on Debian/Ubuntu systems with dynamic templating support.

Requirements
------------

* **Operating System:** Debian or Ubuntu Linux distribution.
* **Privileges:** Sudo / Root access (`become: true`) to install packages and manage systemd services.
* **Ansible Version:** `>= 2.14`


Dependencies
------------

None. This role does not depend on any third-party roles or collections from Ansible Galaxy.

Example Playbook
----------------

### Basic Usage (Localhost)

```yaml
---
- name: Set up local Nginx
  hosts: localhost
  connection: local
  become: true

  roles:
    - role: nginx-locally
