# MacOS Setup with Ansible

This repository contains an Ansible configuration for setting up a Mac from scratch. It's primary purpose is setting up a new Mac from scratch, but I endeavor to also use it for adding new software as I go so that it remains up to date. At the moment it's being used for setting up M1 based Macs running MacOS Monterey.

## Getting Started

There's a simple shell script in `./bin/bootstrap` which will perform the initial steps of:

1. Installing Xcode
2. Installing Ansible
3. Fetching required Ansible roles and collections

And then runs the main playbook `ansible_osx.yml`.

For future updates, `./bin/apply` can be used to run just the Ansible playbook without the setup commands.

## What's installed

The easiest way to understand what's installed is to read the contents of `ansible_osx.yml`, this configuration is fairly specific to the range of development I do personally, but may serve as a useful starting point for others. The core components are:

- ZSH + Oh My Zsh as the primary shell
- Homebrew for package management
- ASDF for version management (along with plugins and default versions for ruby, python, javascript, elixir and erlang)
- Virtualbox, Vagrant and Docker
- VSCode + default plugins and configuration
- A selection of Android SDK's
- Lots of other tools and utilities

## Customising

Everything can be customised by editing `ansible_osx.yml`.

Adding homebrew applications, see https://formulae.brew.sh/ to determine if it is an application or cask.

Adding Mac OSX applications, see https://github.com/geerlingguy/ansible-role-mas#role-variables:
> A list of apps to ensure are installed on the computer. You can get IDs for all your existing installed apps with `mas list`, and you can search for IDs with `mas search [App Name]`. The name attribute is not authoritative and only used to provide better information in the playbook output.