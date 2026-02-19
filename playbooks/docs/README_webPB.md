# Web Deployment Playbook (webPB.yml)

## Executive Summary

This playbook automates web server installation and configuration using
a structured Ansible role.

Developed in a lab environment while following enterprise-grade
deployment principles.

------------------------------------------------------------------------

## Business Value

-   Standardizes web server configuration
-   Enables rapid deployment
-   Ensures configuration consistency
-   Supports scalable rollout
-   Aligns with CI/CD workflows

------------------------------------------------------------------------

## Architecture Overview

Playbook: `playbooks/webPB.yml`\
Role Used: `roles/webdeploy`

Role Components:

-   tasks/main.yml → Installation and configuration workflow
-   templates/httpd.conf.j2 → Parameterized server configuration
-   templates/site.conf.j2 → Virtual host configuration
-   files/welcome.html → Static content deployment
-   handlers/main.yml → Controlled restart logic

------------------------------------------------------------------------

## Inventory Strategy

Built and validated in a small lab with limited nodes.\
Because of the scale, group_vars were not required in this iteration.

Current structure:

-   inventory/hosts
-   host_vars for OS-specific customization

Architecture supports:

-   group-based deployments
-   Environment segmentation (dev / test / prod)
-   Variable hierarchy extension
-   Dynamic inventory integration

The implementation reflects production-level understanding even within a
minimal lab topology.

------------------------------------------------------------------------

## Deployment Workflow

1.  Install web package
2.  Deploy templated configuration
3.  Deploy static content
4.  Enable and start service
5.  Restart only on change

------------------------------------------------------------------------

## Execution

``` bash
ansible-playbook -i inventory/hosts playbooks/webPB.yml
```

------------------------------------------------------------------------

## Project Context

This project demonstrates modular automation, template-driven
configuration management, handler-controlled service orchestration, and
clean separation of logic and variables.

It represents practical infrastructure automation experience built from
hands-on lab engineering and structured using production-ready Ansible
design principles.
