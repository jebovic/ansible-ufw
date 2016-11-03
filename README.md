UFW
===

[![Build Status](https://travis-ci.org/jebovic/ansible-ufw.svg?branch=master)](https://travis-ci.org/jebovic/ansible-ufw) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.ufw-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/ufw)

Install and configure ufw

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Role Variables
--------------

```yaml
# UFW install configuration
ufw_packages:
  - ufw

# UFW basic configuration
ufw_ipv6: "yes"
ufw_default_input_policy: DROP
ufw_default_output_policy: ACCEPT
ufw_default_forward_policy: DROP
ufw_default_application_policy: SKIP
ufw_logging: "off"

# UFW service configuration
ufw_state: enabled
ufw_reset: yes

# UFW custom configuration
ufw_rules: [{ port: 22, rule: allow }]
ufw_applications: []
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.ufw }
```

Tags
----

* ufw_reset : only reset firewall rules
* ufw_config : only update config and reload firewall

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic