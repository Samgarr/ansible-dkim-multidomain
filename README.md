# ansible-dkim-multidomain
Customized ansible-dkim role for multiple domains on server and usage with host_vars.
Tested on Debian Wheezy.

### Example
`host_vars/domain.com`
```yaml
---
dkim_dom:
  - maildomain1.com
  - maildomain2.com
  - maildomain3.com
```

`mailservers.yaml`
```yaml
---
- hosts: mailservers
  roles:
    - { role: ansible-dkim-multidomain, dkim_selector: mail, dkim_domains: "{{ dkim_dom }}" }
```
