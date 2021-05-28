# Ansible Playground

## Basics

```
pip3 install ansible
```

Ansible looks for a config in the following order, c.f. [Ansible Configuration Settings](https://docs.ansible.com/ansible/latest/reference_appendices/config.html) :

```bash
ANSIBLE_CONFIG # environment variable if set
./ansible.cfg  # in the current directory
~/.ansible.cfg # in the home directory
/etc/ansible/ansible.cfg
```

This is why we have a local `ansible.cfg`.

You need a local `hosts` file:

```
touch hosts
```

Install the following roles:

```bash
ansible-galaxy install dokku_bot.ansible_dokku
ansible-galaxy install geerlingguy.docker
```

Now you should be able to runn the playbook:

```
ansible-playbook dokku.yaml
```

## Todo

-[ ] `ansible-galaxy install -r requirements.yml`
-[ ] use git rather than the buggy `dokku git:sync`, c.f. [registering variables with a loop](https://docs.ansible.com/ansible/latest/user_guide/playbooks_loops.html#registering-variables-with-a-loop)


## Notes

```bash
ansible all -a "/bin/echo hello"
```