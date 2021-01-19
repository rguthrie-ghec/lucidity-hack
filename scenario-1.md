# Scenario 1: Project Set up & Initial Deployment

## Summary

Your goal is to successfully launch a new Lucidity Azure DevOps project using supplied tools and to deploy the included canonical application to Azure.

**Notes:**

The application Docker Image is already on DockerHub and is configured in the canonical application environment variables.

A Lucidity Dev Container configuration is provided to speed up local environment set up and it’s recommended it to utilize it in a code space or through VS Code

Before running the infrastructure pipeline, please go into your newly created Terraform-Code repo and make the following change.

* Navigate to Terraform-Code/environment/dev
* Edit the file dev.03_webapp.env
* Change the value of this environment variable TF_VAR_APP_NAME=appeshopdev.
* Instead of appeshopdev, please use a globally unique name as this will be deployed as an AppService in your Azure subscription. If the name is not unique, the deployment will fail.

## Success Criteria

* A new Azure DevOps Project should be created.
* The canonical application (EShop on web) and its corresponding database should be deployed via pipelines to the dev environment.

## References

* [Project Lucidity Install Document](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FPROJECT_INSTALLATION.md&_a=preview)
* [Project Lucidity Install Script Flags](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FINSTALL_SCRIPT_FLAGS.md&_a=preview)
* [Lucidity Dev Container Repo](https://github.com/rguthrie-ghec/lucidity-hack)
* [GitHub CodeSpaces](https://github.com/features/codespaces)
* [VS Code Dev Containers](https://code.visualstudio.com/docs/remote/containers)
