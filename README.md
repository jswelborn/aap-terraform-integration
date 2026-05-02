# aap-terraform-integration

This repository integrates HCP Terraform with Red Hat Ansible Automation Platform.

## Flow

HCP Terraform → Run Task → EDA Rulebook → Post Apply Job → AAP Workflow

## Components

- rulebooks/terraform.yaml
  - Listens for Terraform events

- playbooks/terraform_cloud_post_apply.yaml
  - Determines VM changes
  - Launches appropriate AAP workflow

## Requirements

- AAP with Event-Driven Ansible enabled
- HCP Terraform Run Task configured
- AAP workflow templates already created (e.g. linux-bootstrap)