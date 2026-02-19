## Ansible Projects

   A collection of production-ready Ansible playbooks for Linux infrastructure automation and management.

## Repository Structure 

  - **inventory/** Hosts and group definitions for multi-node orchestration.
  - **roles/** Modular Ansible roles encapsulating reusable tasks.
  - **lnxhd.yml** Playbook for Linux host configuration and baseline setup.
  - **lvmpro.yml** Playbook for automating Logical Volume Management (LVM) provisioning using `community.gene    ral.lvg` and `lvol` modules.
  - **webPB.yml** Playbook for deploying and configuring web servers with idempotent service management.
  - **README.md** Documentation for repository usage and project overview. ---


## Prerequisites

   - **Ansible**: 2.9 or higher
   - **Python**: 3.6 or higher
   - **SSH Access**: To target hosts with appropriate credentials

## Usage

   - bash
   - git clone https://github.com/Johnson-S1/Ansible-Projects.git
   - cd Ansible-Projects

## Update the inventory/ file with your host details

## Run a playbook:
   - ansible-playbook -i inventory lnxhd.yml 
   - ansible-playbook -i inventory lvmpro.yml 
   - ansible-playbook -i inventory webPB.yml

## For more details about My playbooks, I kindly ask you to gothrough my playbook docs:
   - /Ansible-Projects/playbooks/docs
