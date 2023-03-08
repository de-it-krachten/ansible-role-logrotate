[![CI](https://github.com/de-it-krachten/ansible-role-logrotate/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-logrotate/actions?query=workflow%3ACI)


# ansible-role-logrotate

Installs & configures logrotate (bundled with all Linux distros)



## Dependencies

#### Roles
- deitkrachten.cron

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 36
- Fedora 37

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# List of packages
logrotate_packages:
  - logrotate
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'logrotate'
  hosts: all
  become: "yes"
  roles:
    - deitkrachten.showinfo
    - deitkrachten.cron
  tasks:
    - name: Include role 'logrotate'
      ansible.builtin.include_role:
        name: logrotate
</pre></code>
