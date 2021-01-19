# Scenario 5: Testing and Code Quality (optional)

## Summary

The goal of this scenario is to explore the aspects of Lucidity that related to code quality. This include Credential Scanning , Unit Tests and Functional Tests.

### Credential Scanning
Lucidity relies on CredScan in order to detect credentials and secrets in the source code. Take a look at the infrastructure template and try to understand how Cred Scan is used in this project.

### Integration & Unit Testing
Unit testing in Lucidity tests the helper methods used by the integration tests. These are invoked in the validation stage of the infrastructure pipeline.
Integration Tests run as part of the infrastructure pipeline and after each layer.

## Success Criteria

* Write a test to verify that the resource group created in challenge 2 was deployed.

## References

* [Golang Build Tags](https://www.digitalocean.com/community/tutorials/customizing-go-binaries-with-build-tags)
* [Terratest](https://github.com/gruntwork-io/terratest)
* [Terratest Azure Example](https://github.com/gruntwork-io/terratest/tree/master/examples/azure)
* [Terratest Resource Group Module](https://github.com/gruntwork-io/terratest/blob/d2eada2d8542026fdde0224b0e6b26b3445591ee/modules/azure/resourcegroup.go)
