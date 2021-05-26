# Ansible Playground

## Basics

```
brew install ansible@4
```

Ansible looks for a config in the following order, c.f. [Ansible Configuration Settings](https://docs.ansible.com/ansible/latest/reference_appendices/config.html) :

```bash
ANSIBLE_CONFIG # environment variable if set
./ansible.cfg  # in the current directory
~/.ansible.cfg # in the home directory
/etc/ansible/ansible.cfg
```

This is why we create a local `ansible.cfg`:

```
touch ansible.cfg
```

It contains the following

```bash
# ansible.cfg
[defaults]
# If inventory is not set, defaults to /etc/ansible/hosts.
#
# Relative paths are relative to the `ansible.cfg`.
inventory = ./hosts

# If no remote user is set, it defaults to the current user.
remote_user = root

# Set host_key_checking to “False” if you want to avoid host
# key checking by the underlying tools Ansible uses to connect
# to the host
host_key_checking = False
```

```
ansible all -a "/bin/echo hello"
ansible-playbook dokku.yaml
```