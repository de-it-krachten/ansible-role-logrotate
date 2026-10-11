[![CI](https://github.com/de-it-krachten/ansible-role-logrotate/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-logrotate/actions?query=workflow%3ACI)


# ansible-role-logrotate

Installs & configures logrotate (bundled with all Linux distros)



## Dependencies

#### Roles
- deitkrachten.cron

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- Red Hat Enterprise Linux 10<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- RockyLinux 10
- OracleLinux 8
- OracleLinux 9
- OracleLinux 10
- AlmaLinux 8
- AlmaLinux 9
- AlmaLinux 10
- Debian 12 (Bookworm)
- Debian 13 (Trixie)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Ubuntu 26.04 LTS
- Fedora 43
- Fedora 44<sup>1</sup>

Note:
<sup>1</sup> : no automated testing is performed on these platforms


## Role Variables
### defaults/main.yml
<pre><code>
# List of packages
logrotate_packages:
  - logrotate

# Scheduler to use (systemd or cron)
logrotate_scheduler: systemd

# Scheduler timer (defaults to midnight)
logrotate_schedule_time: "00:00:00"
</pre></code>

### defaults/family-RedHat-8.yml
<pre><code>
# Scheduler to use (systemd or cron)
logrotate_scheduler: cron
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'logrotate'
  hosts: all
  become: 'yes'
  roles:
    - deitkrachten.cron
  tasks:
    - name: Include role 'logrotate'
      ansible.builtin.include_role:
        name: logrotate
</pre></code>
