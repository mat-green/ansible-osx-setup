# Zorin OS Setup With Ansible

This repository intends to help with the set up of a minimum Zorin OS installation. It's primaray objective is to set up a new PC/Laptop and keep an audit of the configuration.

## Getting Started

There is a simple shell script in `./bin/boostrap` which will perform the initial steps of:

1. Install Python.
1. Install Ansible.
1. Fetch the required Ansible roles and collections.
1. Run the playbook `ansible_zorin_os.yml`.

For future updates, `./bin/appy` can be used to run just the Ansible playbook without the setup commands.
