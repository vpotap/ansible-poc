# POC Node.js Application Deployment with Ansible

## Overview

This is a Proof of Concept (POC) Ansible project for deploying a production-ready Node.js application using Nginx, PM2, MongoDB, and Node.js. The project uses a single virtual machine (VM) for demonstration purposes, and it has been tested on various Linux distributions. However, Debian 12 is not yet supported, and a workaround is required for its installation.

The project does not aim to provide a comprehensive setup for a Linux environment with essential security best practices, such as the using of UFW, Fail2Ban, and Ansible community security roles for VM hardening. Security provisioning for different Linux distributions should be handled separately using distinct Ansible roles and playbooks

Community roles and collections used in this project include `community.mongodb` and `geerlingguy.nodejs`.

## Getting Started

Follow the steps below to set up and run this project:

1. Create a sudo user and set up passwordless sudo using only SSH key-based authentication. If you only have a root user, it is advisable to create a separate Ansible passwordless user and use SSH key-based authentication.

   **Note:** Vagrant automatically creates a user for you.

2. Run the Ansible roles and collection installation script:

   ```bash
   chmod +x install_roles_and_collections.sh
   ./install_roles_and_collections.sh
   ```

3. Edit the `/etc/hosts` file and add the following line (you can also use the Vagrant plugin to update `/etc/hosts`):

   ```
   127.0.0.1   hw.local
   ```

4. Spin up the VM by running the following command (check the Vagrantfile for supported distributions):

   ```bash
   vagrant up debian11
   ```

5. Check and update application variables in the `/group_vars/all.yml` file.

6. Check and update path and version variables in the `/vars/main.yml` file.

7. Examine the `inventory.ini` file to review Ansible groups, hosts, and users (a default user is provided with Vagrant).

8. Run VM provisioning with the following command:

   ```bash
   ansible-playbook -i inventory.ini main.yml --flush-cache -vv
   ```

## To-Do List

Here are some additional tasks and improvements that can be done in this project:

1. Configure log rotation for all processes (Nginx, MongoDB, PM2, etc.).
2. Implement better management of PM2 with further research.
3. Utilize community roles for setting up Nginx with Certbot support.
4. Install Node.js using NVM for better control over Node.js and npm versions.
5. Use Ansible Vault to protect and hide passwords in the Git repository.
6. Conduct a security audit for the application and VM, and apply popular security roles and custom playbooks for VM hardening. Install and configure SSL, UFW, Fail2Ban, etc.
7. Install basic monitoring and/or metrics exports, for example, Prometheus and Grafana.
8. Apply configurations for the Linux distribution kernel to handle high loads effectively.

Feel free to refer to this README for guidance on setting up and enhancing your Node.js application deployment project.