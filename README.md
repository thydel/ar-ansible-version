# ansible-version

An ansible role to embed ansible_version module

- Embed eponymous module to get `ansible_version` available as an ansible fact.
- The galaxy role is name `version-ansible` because galaxy auto-remove `ansible` prefix.

## Requirements

I dont know if ``__version__`` is available for all ansible version

## Role Variables

None

## Dependencies

Use embedded eponymous module

## Example Playbook

``` yaml
- hosts: localhost
  gather_facts: False

  roles:
    - role: ansible-version

  tasks:
	- local_action: ansible_version
	- set_fact: mode=0400
	- when: ansible_version | version_compare('1.8', '>=')
	  set_fact: mode=a-x
```

## License

BSD

## Author Information

Thierry Delamare
