
# ==================================================
# FILE 1: prerequisites/tasks/main.yml
# ==================================================

---
# tasks file for prerequisites

- name: Install git
  apt:
    name: git
    state: present
    update_cache: yes


# ==================================================
# FILE 2: PostgreSQL/tasks/main.yml
# ==================================================

---
# tasks file for PostgreSQL

- name: Install PostgreSQL
  apt:
    name: postgresql
    state: present
    update_cache: yes

- name: Start PostgreSQL service
  systemd:
    name: postgresql
    state: started
    enabled: yes


# ==================================================
# FILE 3: apache/tasks/main.yml
# ==================================================

---
# tasks file for apache

- name: install Apache web server
  apt:
    name: apache2
    state: present
    update_cache: yes


# ==================================================
# FILE 4: stack.yml
# ==================================================

---
- hosts: localhost
  become: true
  roles:
    - prerequisites
    - PostgreSQL
    - apache
