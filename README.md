# Ansible Playbook for Apache Web Server Installation and Management on AWS EC2

## Introduction

### Purpose of the Playbook

This Ansible playbook automates the installation, start, and stop procedures for the Apache web server on an AWS EC2 instance running Ubuntu. It simplifies the process of setting up a web server for hosting web content.

### Target Environment

This playbook is designed for an environment where an AWS EC2 instance is used as a web server, and Ansible is employed for automation.

# Prerequisites

### Ansible Installation

Ensure that Ansible is installed on your local machine. You can install it using your package manager.


# For example, on Ubuntu
**sudo apt update
sudo apt install ansible**

# AWS EC2 Instance Setup

Launch an AWS EC2 instance running an Ubuntu-based AMI. Take note of the instance's public IP or DNS.
# AWS SSH Key Configuration

Configure your AWS SSH key (.pem file) for authentication when connecting to the EC2 instance.
# Inventory Setup
# Creation of the inventory.ini file

Create an inventory file called inventory.ini in a directory of your choice. This file defines the hosts to be managed by Ansible.
# Define the [webserver] group

In the inventory file, define a group named [webserver] to specify the target hosts for this playbook.

ini

[webserver]
**ec2-instance-public-ip ansible_ssh_private_key_file=/path/to/your/aws-ssh-key.pem**

Replace ec2-instance-public-ip with the actual IP or DNS of your EC2 instance and provide the correct path to your AWS SSH key.
Playbook Explanation
Playbook Structure

The playbook is structured into multiple tasks. Each task has a specific purpose in the installation and management of Apache.
# Task Descriptions

    Update Package Cache: Ensures that the package cache is up-to-date on the target system.
    Install Apache: Installs the "apache2" package on the target system if it's not already installed.
    Start Apache: Initiates the Apache service to make the web server accessible.
    Stop Apache: Optionally stops the Apache service, useful for maintenance or configuration changes.

# Troubleshooting Common Inventory Issues
# Permission Denied when Creating the Inventory File

If you encounter a "Permission Denied" error when creating the inventory file, you may need to use sudo or navigate to a directory where you have write permissions.
# Matching Hosts with Host Patterns

Ensure that the host patterns in your playbook match the group names defined in the inventory file.
# Configuring SSH for Inventory

Make sure your SSH private key is correctly configured in the inventory file and accessible at the specified path.
# Running the Playbook
# Executing the Playbook

Use the ansible-playbook command to run the playbook, specifying the inventory file and playbook name. For example:


**ansible-playbook -i inventory.ini playbook1.yml**

# Reviewing the Playbook Output

After running the playbook, review the output to confirm that the tasks were executed successfully.
# Conclusion
# Summary of the Playbook's Purpose

This playbook simplifies the process of installing and managing the Apache web server on an Ubuntu-based AWS EC2 instance.
