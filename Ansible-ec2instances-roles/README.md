# EC2 Instance Deployment with Ansible

This project demonstrates how to create multiple EC2 instances on AWS using **Ansible**. The instances are created dynamically in a loop, and all configuration inputs are parameterized using variables. Sensitive credentials are securely managed through an Ansible Vault pass file.

## Prerequisites

Before running the Ansible playbooks, ensure that you have the following tools and configurations set up:

- **AWS Account** with proper IAM permissions to create EC2 instances.
- **Ansible** installed on your local machine.
- **AWS CLI** installed and configured with your credentials.
- **Ansible Vault** passphrase file for securely storing sensitive data.
- **Python Boto3** library installed for Ansible to interact with AWS.

### To Run the Ansible role

- ansible-playbook my-playbook.yml --vault-password-file vault.pass

