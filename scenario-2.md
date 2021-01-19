# Scenario 2: Pull Request Workflow

## Summary

In this scenario, the goal is to introduce a simple change to the terraform and see it deployed to Azure. For the sake of time, the change should be fairly simple and it’s recommended to simply go with creating a new empty resource group.

A core focus of this challenge is ensuring the change goes through a feature branch and pull request to ensure engineering best practices are applied.

**Notes:**

* Take a look at existing pipelines and environments to see what has been configured.  

* Take note of any build validation steps that have been added to the Terraform-Pipelines or Terraform-Code repos.

## Success Criteria

* A new Resource Group, with a name of your choosing, should be deployed to Azure.
* Demonstrate that the new RG has gone through the pull request process and that the change was validated in a PR environment/pipeline before being deployed to the dev environment.
* Optional: Use a name module to generate a unique name.

## References

* [Project Lucidity PR Pipeline Scenarios](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FPRPIPELINESCENARIOS.md&_a=preview)
* [Project Lucidity Pipelines](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FPIPELINES.md&_a=preview)
* [AzureRM Naming Module](https://github.com/Azure/terraform-azurerm-naming)