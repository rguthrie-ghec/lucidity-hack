# Scenario 3: Working with Layers

## Summary

The focus of this scenario is to learn to use Project Lucidity Layers. Layers offer an easy mechanism to segment infrastructure deployments. Lucidity offers two important constructions; Layers and Deployments.

* Deployments: Individual terraform modules that are part of a tech stack. Deployments are executed in Parallel in a layer.

* Layers: Provides a way to group together deployments. Layers are executed in sequential order.

Example:

```
02-Networking
  01-Deploy Custom VNET
  02-Configure Storage Accounts.
  
03-AppLayer
  01-Deploy AKS
  02-Deploy ACR
```

Note:

* From an implementation point of view, layers and deployments are folder structure under the terraform folder of the Terraform-Code repo.
* Project Lucidity automatically configures a special layer called 01-Init. This used to configure an Azure Storage account to host Terraform Remote State. This layer is excluded from the infrastructure pipeline and used specifically by the storage init pipeline.

**Notes:**

* Look at existing pipelines and environments to see what has been configured.  
* Take note of any build validation steps that have been added to the Terraform-Pipelines or Terraform-Code repos.

## Success Criteria

* Demonstrate that the Resource Group added in challenge 2 is now managed in a new Layer (layer 4)
* Deploy new Resource group in layer 4.
* Deploy new Storage Account in layer4.
* Ensure Static Website is enabled.
* Include a simple HTML page and deploy it to the storage account website.

## References

* [Understanding Lucidity Layers video](https://msit.microsoftstream.com/video/c632a4ff-0400-b9eb-0154-f1eb39bceb8a?channelId=8855a1ff-0400-b9ec-aeb5-f1eb39bb3013)
* [Storage Init Pipeline Video](https://msit.microsoftstream.com/video/c632a4ff-0400-b9eb-0848-f1eb39bd1f3c?channelId=8855a1ff-0400-b9ec-aeb5-f1eb39bb3013)
* [Infrascture Pipeline](https://msit.microsoftstream.com/video/5d5ba1ff-0400-b9eb-40b9-f1eb39eee392?channelId=8855a1ff-0400-b9ec-aeb5-f1eb39bb3013)
* [Directory Structure Documentation](https://dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines?path=%2Fdocs%2FDIRECTORY_STRUCTURE.md&_a=preview)