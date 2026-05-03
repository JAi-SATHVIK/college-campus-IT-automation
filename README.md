# College Campus IT Infrastructure Automation using Ansible

A complete multi-node infrastructure automation project built with Ansible to provision, configure, secure, and manage a simulated college campus IT environment across multiple Red Hat Enterprise Linux servers.

This project demonstrates enterprise-grade Infrastructure as Code (IaC) practices by automating:

- User management
- Package installation
- Service configuration
- Web server deployment
- Database server setup
- Firewall hardening
- Role-based reusable automation
- Secrets management using Ansible Vault
- Template-based configuration deployment
- Collection usage
- Tag-based selective execution

---

## Project Overview

Manual server administration in educational institutions is repetitive, error-prone, and difficult to scale. This project solves that problem by automating the deployment and configuration of a college campus IT infrastructure using Ansible.

The automation provisions four different managed servers from a single control node:

| Hostname | Purpose |
|----------|---------|
| workstation | Ansible Control Node |
| servera | Student User Management Server |
| serverb | College Web Portal Server |
| serverc | Student Records Database Server |
| serverd | Faculty/Admin Services Server |

The system enables one-click deployment of the entire infrastructure using a single Ansible playbook.

---

## Objectives

- Automate repetitive Linux administration tasks
- Implement reusable Ansible roles for modular automation
- Configure web, database, and user services across multiple hosts
- Apply firewall rules for service-level security
- Secure sensitive credentials using Ansible Vault
- Demonstrate real-world Infrastructure as Code concepts

---

## Technologies Used

- Red Hat Enterprise Linux 9
- Ansible Automation Platform / Ansible Core
- YAML
- Apache HTTP Server
- MariaDB Server
- Firewalld
- Git & GitHub
- Ansible Vault
- Ansible Galaxy Collections

---

## Ansible Concepts Covered

This project implements all major RH294 automation concepts:

- Inventory Management
- ansible.cfg Configuration
- Variables and group_vars
- Ansible Vault
- Playbooks
- Roles
- Tasks
- Handlers
- Templates (Jinja2)
- Tags
- Collections
- Firewalld Automation
- Service Management
- Package Management
- User Management

---

## Project Architecture

```text
                     +----------------------+
                     |     workstation      |
                     |  Ansible Control Node|
                     +----------+-----------+
                                |
        ---------------------------------------------------------
        |                    |                    |              |
        v                    v                    v              v
+---------------+   +---------------+   +---------------+  +---------------+
|    servera    |   |    serverb    |   |    serverc    |  |    serverd    |
| Student Users |   | Web Portal    |   | MariaDB       |  | Faculty/Admin  |
| User Accounts |   | Apache Server |   | DB Services   |  | Faculty Users  |
+---------------+   +---------------+   +---------------+  +---------------+
```
---
## Directory Structure

```
college-campus-it-automation/
│
├── ansible.cfg
├── inventory
├── site.yml
├── requirements.yml
├── README.md
│
├── group_vars/
│   └── all.yml
│
├── vault/
│   └── secrets.yml
│
└── roles/
    ├── common/
    ├── user_management/
    ├── web_portal/
    ├── database_records/
    └── firewall_security/
```
---
## Clone Repository
```
git clone https://github.com/YOUR_USERNAME/college-campus-it-automation.git
cd college-campus-it-automation
```
## Verify Inventory Connectivity
```
ansible all -m ping
```
## Syntax Validation
```
ansible-playbook site.yml --syntax-check
```
## Execute Full Infrastructure Deployment
```
ansible-playbook site.yml --ask-vault-pass
```
## Execute Specific Components using Tags
```
ansible-playbook site.yml --tags students --ask-vault-pass
ansible-playbook site.yml --tags web --ask-vault-pass
ansible-playbook site.yml --tags db --ask-vault-pass
ansible-playbook site.yml --tags firewall --ask-vault-pass
```
## Verify Student Users
```
ansible labservers -m shell -a "cat /etc/passwd | grep student"
```
## Verify Faculty Users
```
ansible facultyservers -m shell -a "cat /etc/passwd | grep faculty"
```
## Verify Web Portal
```
curl http://serverb
```
## Verify Database Service
```
ansible dbservers -m shell -a "systemctl status mariadb"
```
## Verify Firewall Configuration
```
Verify Firewall Configuration
```
---
