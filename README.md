# ansible-playbooks
Ansible playbooks and config for homelab automation

## Common commands

### Run a playbook
```bash
ansible-playbook setup_vps.yml -i inventory/default.yml -K -J --limit "str-vps-01"
```

### Switches explained
- `-i inventory/default.yml` - inventory file to use
- `-K` - ask for sudo password
- `-J` - ask for vault password
- `--limit "str-vps-01"` - limit playbook to a specific host
- `--tags "tag1,tag2"` - run only specific tags
- `--skip-tags "tag1,tag2"` - skip specific tags
- `--check` - dry-run mode

### Run a single role
```bash
ansible <hosts> -i inventory/default.yml --module-name include_role --args name=<role_name>
```

### Test connection with ping
```bash
ansible -m ping all -i inventory/default.yml
```

### Encrypt a variable 
```bash
ansible-vault encrypt_string --vault-id @prompt --name <variable>
```