# Scenario 1: Project Set up & Initial Deployment

## Summary

Your goal is to successfully launch a new Lucidity Azure DevOps project using supplied tools and to deploy the included canonical application to Azure.

**Notes:**

The application Docker Image is already on DockerHub and is configured in the canonical application environment variables.

A Lucidity Dev Container configuration is provided to speed up local environment set up and it’s recommended it to utilize it in a code space or through VS Code

## Success Criteria

* A new Azure DevOps Project should be created.
* The canonical application (EShop on web) and its corresponding database should be deployed via pipelines to the dev environment.

## References

* [Local Development Setup (Dev container recommended!)](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FLOCAL_DEVELOPER_SETUP.MD&_a=preview)
* [Project Lucidity Install Document](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FPROJECT_INSTALLATION.md&_a=preview)
* [Project Lucidity Install Script Flags](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FINSTALL_SCRIPT_FLAGS.md&_a=preview)
* [Infrastructure Pipeline Deployment Modes](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FINFRASTRUCTUREPIPELINEOPERATIONS.md&_a=preview)
* [VS Code Dev Containers](https://code.visualstudio.com/docs/remote/containers)
