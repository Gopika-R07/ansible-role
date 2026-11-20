
# Exercise 8 - Ansible Roles

## Aim
To install Ansible, configure Ansible roles and write playbooks.

## 1. Install Ansible

```bash
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

Verify:

```bash
ansible --version
```

## 2. Navigate to Ansible directory

```bash
cd /etc/ansible/
```

## 3. Create the three roles

```bash
sudo ansible-galaxy init prerequisites
sudo ansible-galaxy init PostgreSQL
sudo ansible-galaxy init apache
```

## 4. Configure role YAML files

Edit the following files and copy their corresponding content from YAML_FILES.md:

- prerequisites/tasks/main.yml
- PostgreSQL/tasks/main.yml
- apache/tasks/main.yml

## 5. Create the main playbook

```bash
sudo nano /etc/ansible/stack.yml
```

Copy the stack.yml section from YAML_FILES.md.

## 6. Execute the playbook

```bash
sudo ansible-playbook stack.yml
```

## 7. Verify installation

```bash
git --version
apache2 -v
sudo systemctl status postgresql
sudo systemctl status apache2
```

## Result

Thus, Ansible was installed, three roles were
configured and the stack playbook was executed successfully.
