# jychoy92 Ansible Collections

| Collection                        | Description                                     |
| -------------                     | -------------                                   |
| [sample](sample/)                 | Sample collection for you to experience ansible |
| [packages_mgmt](packages_mgmt/)   | Manage Linux packages                           |
| [linux_init](linux_init/)         | Linux OS initialization                         |

## Sample Playbook
```yaml
---
- hosts: all
  gather_facts: True
  force_handlers: True
  become: True
  collections:
    - jychoy92.packages_mgmt
    - jychoy92.linux_init
    - jychoy92.sample

  tasks:
    - name: Run role hostname from jychoy92.linux_init
      import_role:
        name: jychoy92.linux_init.hostname

    - name: Run role yum from jychoy92.packages_mgmt
      import_role:
        name: jychoy92.packages_mgmt.yum

    - name: Run role common from jychoy92.sample
      import_role:
        name: jychoy92.sample.common
```