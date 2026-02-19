# Linux Hardening Playbook (lnxhd.yml)

## Executive Summary

This playbook implements baseline Linux security hardening aligned with
enterprise security standards.\
It enforces SSH security policies, firewall controls, and SELinux
configuration using a modular role-based Ansible architecture.

Built in a controlled lab environment and structured using
production-ready design patterns.

------------------------------------------------------------------------

## Business Value

-   Enforces standardized security controls
-   Reduces configuration drift
-   Improves audit readiness
-   Enables repeatable compliance enforcement
-   Minimizes risk from insecure defaults

------------------------------------------------------------------------

## Architecture Overview

Playbook: `playbooks/lnxhd.yml`\
Role Used: `roles/hardening`

Role Components:

-   tasks/main.yml → Entry workflow
-   tasks/ssh.yml → SSH security controls
-   tasks/fwall.yml → Firewall configuration
-   tasks/selinux.yml → SELinux enforcement
-   handlers/main.yml → Controlled service restarts
-   templates/ssh_hardening.conf.j2 → Parameterized SSH configuration

------------------------------------------------------------------------

## Inventory Strategy

This project was developed in a small lab environment with limited
nodes.\
Because of this, group-level variables were not heavily utilized.

However, the structure supports enterprise scaling:

-   Static inventory file: `inventory/hosts`
-   Host-specific variables:
    -   `inventory/host_vars/cent.yml`
    -   `inventory/host_vars/red.yml`

While group_vars were not required for the lab setup, the architecture
is fully compatible with:

-   group_vars/`<group>`{=html}.yml
-   environment-based inventory segregation
-   dynamic inventory integration

This demonstrates understanding of scalable inventory design even though
the current scope was intentionally minimal.

------------------------------------------------------------------------

## Idempotency & Operational Reliability

-   Declarative Ansible modules
-   Handler-driven service restarts
-   Safe repeated execution
-   No configuration duplication
-   Predictable state enforcement

------------------------------------------------------------------------

## Execution

``` bash
ansible-playbook -i inventory/hosts playbooks/lnxhd.yml
```

------------------------------------------------------------------------

## Project Context

This automation reflects hands-on infrastructure hardening practice
within a controlled lab.\
It demonstrates secure configuration management, modular design, and
production-oriented Ansible structuring.
