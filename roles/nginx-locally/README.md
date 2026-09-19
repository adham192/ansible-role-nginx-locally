Nginx Locally
=============

An Ansible role to install, configure, and manage Nginx locally on Debian/Ubuntu systems with dynamic templating support.

Requirements
------------

* **Operating System:** Debian or Ubuntu Linux distribution.
* **Privileges:** Sudo / Root access (`become: true`) to install packages and manage systemd services.
* **Ansible Version:** `>= 2.14`

Role Variables
--------------

The following variables are defined in `defaults/main.yml` and can be overridden in your playbooks or inventory:

| Variable | Default Value | Description |
| :--- | :--- | :--- |
| `nginx_package_name` | `nginx` | Name of the Nginx package to install. |
| `nginx_service_name` | `nginx` | Name of the systemd service to manage. |
| `nginx_web_root` | `/var/www/html` | Directory path where static web content is deployed. |
| `server_title` | `"Local Nginx Server"` | Header/Title injected into the default `index.html` template. |
| `welcome_message` | `"Configured via Ansible Role"` | Greeting message displayed on the generated landing page. |

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
