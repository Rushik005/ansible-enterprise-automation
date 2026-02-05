# Ansible Enterprise Automation Framework

This repository contains a production-ready Ansible automation framework designed to provision, configure, secure, patch, and deploy applications across multiple environments (dev, staging, prod).

## Features
- Role-based Ansible architecture
- Environment-specific inventories
- OS hardening and security baseline
- Automated patching with reboot handling
- Application deployment with zero manual steps
- CI/CD integration with linting and dry runs
- Secure secret management using Ansible Vault

## Supported Platforms
- Ubuntu 20.04 / 22.04
- RHEL 8 / 9

## Repository Structure
- `inventories/` – Environment-specific hosts and variables
- `roles/` – Modular reusable Ansible roles
- `site.yml` – Master playbook
- `vault/` – Encrypted secrets
- `.gitlab-ci.yml` – CI/CD pipeline

## Usage

### Dry Run
```bash
ansible-playbook -i inventories/dev/hosts.yml site.yml --check
```

### Apply Configuration
```bash
ansible-playbook -i inventories/prod/hosts.yml site.yml
```

### Run Specific Components
```bash
ansible-playbook site.yml --tags "security,patching"
```

## Security
All sensitive data is encrypted using Ansible Vault. No secrets are stored in plaintext.

## Outcome
- Reduced server provisioning time from hours to minutes
- Eliminated configuration drift
- Standardized deployments across environments
