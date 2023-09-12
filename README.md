Configuration as Code
===

This Ansible project contains roles and playbooks that can be used to deploy configuration as code within an AAP environment

Deploying Automation Hub, deploying Controller, and refreshing Automation Hub tokens are the functionalities that are currently supported

## Structure
This repository contains 2 main folders
- `collections:` contains a requirements.yml file which defines collections that will be used by the roles
- `roles:` contains role folders with code that will be used to deploy configuration as code

It also contains the playbooks that get ran to deploy configuration as code

## Collections
| Collection Name | Description |
|:----------------|:------------|
| awx.awx | Allows for easy interaction with AWX servers via |
| ansible.controller | Allows for easy interaction with AAP Controller |
| infra.controller_configuration | Allows for easy interaction and configuration of AAP Controller |
| infra.ah_configuration | Allows for easy interaction and configuration of Automation Hub |

## Roles
| Role Name | Description |
|:----------------|:------------|
| [deploy_aap2_automationhub_configurations](roles/deploy_aap2_automationhub_configurations/) | Used to deploy Automation Hub |
| [deploy_aap2_controller_configurations](roles/deploy_aap2_controller_configurations/) | Used to deploy Controller |

## Usage
1. Run deploy_aap2_automationhub_as_code.yml
2. On Automation Hub:
    - Manually create the validated content
    - Manually sync the validated content
    - Validate all repos/registries and sync status
    - Create an API Token for use between Controller and PAH: Collections > API token > Load token (only needs to be done once)
    -  Create a rh-validated REMOTE repository: Collections > Remotes > Add remote > Enter data and save
    - Create a rh-validated PAH repository: Collections > Repositories > validated > Edit > Select "rh-validated" in "Remote" pull down > Click Save > Click "Sync"   
3.  Run deploy_aap2_controller_as_code.yml

# Licensing
MIT

# Contributions
- Red Hat Consulting