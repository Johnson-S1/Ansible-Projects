# Linux Hardening Playbook

**File**: `lnxhd.yml`

## Overview
Applies security hardening to Linux systems using the hardening role.

## Playbook Details

## What This Does?
   The hardening role performs:
        SSH hardening
        Firewall configuration
        Security updates
        File permissions management
        Service hardening

## Requirements
   Ansible 2.9+
   Target hosts must be in nodes group
   Sudo/root access required
   Linux OS (Ubuntu/CentOS/RHEL)

## Hosts Targeted
    Host Group: nodes
    Sudo/Root: Yes (become: yes)
    Facts Gathering: Yes

## Before Running
   Backup system configurations
   Test in non-production environment first
   Ensure SSH access won't be disrupted
   Review hardening role tasks

## Role Used
     hardening - Applies security hardening configurations

## Usage
   1) Run the playbook
   bash
   ansible-playbook lnxhd.yml

   2) Run with specific inventory
   bash
   ansible-playbook lnxhd.yml -i inventory/hosts

   3) Dry-run mode
   bash
   ansible-playbook lnxhd.yml --check

   4) Verbose output
   bash
   ansible-playbook lnxhd.yml -vv

## Inventory Setup
   Define nodes group in inventory/hosts:
   Note: In my inventory file named nodes.int, i used my server domain plainly based on my preference

   EXAMPLE
   INI
      [nodes]
      ubuntu1 ansible_host=192.168.1.10 ansible_user=ubuntu
      ubuntu2 ansible_host=192.168.1.11 ansible_user=ubuntu

## Related Files
## Role: roles/hardening/
## Inventory: inventory/hosts
## Other playbooks: webPB.yml, lvmpro.yml
