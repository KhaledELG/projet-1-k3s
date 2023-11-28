# Ansible Deployment for K3s Cluster

This project orchestrates the deployment and reset of a K3s cluster using Ansible.

## Configuration

### Variables

Make sure to set the following variables:

- `PUBLIC_IP`: Public IP address of the cluster.
- `PRIVATE_KEY`: Private key for accessing the cluster.
- `PRIVATE_AWS_ACCESS_KEY_ID`: Access key ID for AWS.
- `PRIVATE_AWS_SECRET_ACCESS_KEY`: Secret access key for AWS.
- `INPUT_RESET_CLUSTER`: Indicates whether to reset the cluster (`yes` or `no`).
- `INPUT_DEPLOY_CLUSTER`: Indicates whether to deploy the cluster (`yes` or `no`).

## Pipeline Stages

This pipeline consists of two main stages:

1. **Deploy** (`deploy`): Deploys the K3s cluster using Ansible if `INPUT_DEPLOY_CLUSTER` is set to `yes`.
2. **Reset** (`reset`): Resets the K3s cluster using Ansible if `INPUT_RESET_CLUSTER` is set to `yes`.

Each stage executes Ansible playbooks based on specific conditions defined by the input variables.

## Before Script

The `before_script` section performs the following actions:

- Updates IP addresses and AWS credentials in the Ansible inventory file (`hosts.ini`).
- Sets up necessary Ansible configurations and keys required for deployment and access.

## Execution

### Prerequisites

Ensure the variables and configurations are correctly set before triggering the pipeline.

### Manual Triggering

The `Deploy` and `Reset` stages require manual intervention based on the variables set to prevent unintended cluster operations.
