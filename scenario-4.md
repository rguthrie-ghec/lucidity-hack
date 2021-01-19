# Scenario 4: Infrastructure Pipeline Deployment Modes

## Summary

The goal of this scenario is to introduce deployment modes and specifically Deployment Dir. Your task is to change the static html file deployed in scenario 3 via layers, and run in the infrastructure pipeline via deployment dir to ensure only that only that deployment is run.

### Deployment Modes

When deploying resources via the infrastructure pipeline, there are several modes that can apply. These are controlled via input variables into the deployment pipeline.

* **Full Deployment:** By specifying that the FULL_DEPLOYMENT variable is true, this instructs the infrastructure pipeline to deploy all layers and deployments regardless of whether changes exist or not.

  In this case the stages for that layer will be run and Terraform Plan and Apply will be invoked. Note if the infrastructure has not changed, then Terraform Apply will not make any changes.

* **Deployment Dir:** The DEPLOYMENT_DIR variable allows you to specify a folder path to a specific deployment and is in the format <layer/deployment>. It's expected that this is a valid path under the terraform folder in the Terraform-Code repo.

  By including a deployment dir, you can instruction the Infrastructure Pipeline to only run this specific deployment and skip other deployments/layers.

* **Diff Deployment:**  This method compares two branches an only triggers deployments that have a diff. This is the default behavior for the PR pipeline, but you can also use this deployment type on different environment by specifying the branches to compare against.

  Diff deployments rely on the following two variables:

  * gitDiffBaseBranch - This is the target branch and is often main/master.
  * gitDiffCompareBranch - This is the incoming feature branch with your new changes.

  **For pull request workflows, gitDiffBaseBranch and gitDiffCompareBranch are automatically set.**

## Success Criteria

* Change static website and only redeploy that layer.
Note: There is no need to change the app itself. An image with a small visual change has been pushed to dockerhub, and changing the configruation to use this image will suffice. (this still requires a PR workflow.)
https://hub.docker.com/r/hattan/eshopwebmvc/tags?page=1&ordering=last_updated

## References

* [Deployment modes in Infrastructure Pipeline video](https://msit.microsoftstream.com/video/5d5ba1ff-0400-b9eb-40b9-f1eb39eee392?st=262)
