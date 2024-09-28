Hi, ![](https://user-images.githubusercontent.com/18350557/176309783-0785949b-9127-417c-8b55-ab5a4333674e.gif)my name is Serhii Shypylov
=========================================================================================================================================

💛 I am a Linux System administrator engineer with DevOps practices. I have several certificates in Linux, Docker, Ansible and Terraform and continue to learn more. I like everything related to Docker, containers and IT technologies in general. I love solving complex IT solutions.
-------------------------------

* 💼 Looking for a job
* 🌍 I'm based in Poznan
* 🖥️ See my [LinkedIn](https://github.com/Shipssv83) profile 
* 👾 Chat with IT pros on [Discord](https://discord.com/shipssv_19055)\
* 📧 Reach me at ships@ukr.net
* 🧠 I'm learning DevOps Practices

### Socials

<p align="left"> <a href="https://github.com/Shipssv83" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github.svg" width="32" height="32" /> </picture> </a> <a href="https://www.linkedin.com/in/sergey-shipilov-7262a31b4/" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin.svg" width="32" height="32" /> </picture> </a></p>

# Ansible Playbook for Server, Docker, and GLPI Installation

This project includes Ansible playbooks for setting up a server, installing Docker, and deploying GLPI along with FusionInventory inside Docker containers.

## Overview

The project is structured with the following steps:
1. **Server Setup**: Configures the basic server settings like timezone.
2. **Docker Installation**: Installs Docker and Docker Compose on the target server.
3. **GLPI and FusionInventory Installation**: Deploys GLPI (IT asset management) and FusionInventory in Docker containers, along with MariaDB for the database.

## Playbook Structure

### 1. Server Setup (`server-install.yml`)
This playbook configures the necessary packages and performs basic server setup, such as timezone configuration.

### 2. Docker Installation (`docker-install.yml`)
The `docker-install.yml` playbook installs Docker and Docker Compose to prepare the server for containerization.

### 3. GLPI and FusionInventory Installation (`glpi-docker-install.yml`)
This playbook sets up and installs GLPI (version 10.0.6) and FusionInventory, along with MariaDB for the GLPI database, using Docker containers.

## Variables

The following variables are configurable for this playbook:

- `timezone`: The timezone of the server (default: `Europe/Warsaw`).
- `glpi_version`: The version of GLPI to be installed (default: `10.0.6`).
- `fusioninventory_version`: The version of FusionInventory to be installed (default: `10.0.6`).
- `mariadb_version`: The version of MariaDB to be installed (default: `10.10.2`).
- `email`: Administrator email (default: `admin@example.com`).
- `MARIADB_USER_GLPI`: MariaDB user for GLPI (default: `user_glpi`).
- `MARIADB_PASSWORD_GLPI`: Password for the GLPI MariaDB user (default: `strong_password`).
- `MARIADB_DATABASE_GLPI`: Name of the GLPI MariaDB database (default: `glpi`).
- `MARIADB_ROOT_PASSWORD_GLPI`: Root password for MariaDB (default: `strong_password`).

### Example Configuration:

```yaml
vars:
  timezone: 'Europe/Warsaw'
  glpi_version: '10.0.6'
  fusioninventory_version: '10.0.6'
  mariadb_version: '10.10.2'
  email: 'admin@example.com'
  MARIADB_USER_GLPI: 'user_glpi'
  MARIADB_PASSWORD_GLPI: 'strong_password'
  MARIADB_DATABASE_GLPI: 'glpi'
  MARIADB_ROOT_PASSWORD_GLPI: 'strong_password'
```

# ansible galaxy roles
```
### install role ansible galaxy
ansible-galaxy install -r roles/requirements.yml

### upgrade role ansible galaxy 
ansible-galaxy install -g -f -r roles/requirements.yml
```

# Run the Playbook install
Run the playbook by specifying your inventory file and variable file:

```
ansible-playbook -i inventory --user root --extra-vars "host=host_name" playbooks/glpi-install.yml
```


This README provides a structured guide for installing a server, Docker, and the GLPI system with FusionInventory using the provided playbook.

License
This project is licensed under the MIT License