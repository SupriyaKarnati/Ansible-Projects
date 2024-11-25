# Apache Installation and Configuration with Ansible

This Ansible playbook automates the installation, configuration, and management of the Apache web server on your target hosts. It utilizes **Ansible roles** to organize tasks for reusability and **handlers** to manage service restarts when configurations are updated.

## Features

- Installs Apache using the appropriate package manager for the target system (e.g., `apt` for Ubuntu, `yum` for CentOS).
- Starts the Apache service and ensures it is enabled to start on boot.
- Utilizes Ansible **roles** to organize tasks for reusability.
- Defines **handlers** to restart Apache only when there are changes to the configuration.
- Configurable variables for Apache package and service names to support different environments.

## Requirements

- Ansible 2.x or higher
- Managed hosts must have Python and the required package managers (e.g., `apt`, `yum`, etc.) installed.
- Ensure that Ansible has SSH access to your target machines.
