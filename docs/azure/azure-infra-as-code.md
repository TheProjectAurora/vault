# Infrastructure as Code in Azure

Infrastructure as Code is the modern way to provision resources in the cloud. Instead of hand crafting the service through the web console you define the desired state in files that can be stored in version control. This gives you the capability to rebuild your production system when something goes wrong.

With Azure you have different options to choose from. Let's go through the pros and cons for each of them.

## ARM Templates

[Azure Resource Manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/overview) (ARM) is the service that handles all resource deployment and management whether you were using the Azure portal, CLI, PowerShell or REST clients.

ARM templates are JSON files that define the needed resources and their configurations. You can then perform the deployment from the command line using PowerShell or Azure CLI, or the template can be used in a continuous integration pipeline.

**Pros**

- automatically feature-complete

**Cons**

- it is JSON

## Bicep

[Bicep](https://github.com/Azure/bicep) is the new Domain Specific Language that can be used to define ARM templates in a declarative way. The Bicep language has its own syntax which is then transparently transpiled to a valid ARM template.

In order to get started you need to have the Bicep CLI. You can also install the Bicep VS Code extension for a nicer experience on Visual Studio Code. Just follow the [official installation instructions](https://github.com/Azure/bicep/blob/main/docs/installing.md).

**Pros**

- automatically feature-complete
- not JSON
- existing ARM templates can be automatically migrated

**Cons**

- Azure only
- yet another syntax to learn

## Terraform

[Terraform](https://www.terraform.io/) is a popular IaC tool that supports all major clouds. When you learn it once you can transfer those skills to other clouds too.

It is independent of the cloud providers and open source, so it's not favouring one cloud provider over the other. Terraform enables you to configure reproducible multi-cloud environments.

[Atlantis](https://www.runatlantis.io/) adds another layer on top of Terraform management by automating the deployments through a pull request workflow. It listens to webhooks from GitHub, GitLab, Bitbucket or Azure DevOps and interacts with you through pull request comments.

**Pros**

- supports all major clouds
- skills are applicable in a wider array of projects

**Cons**

- it might take some time until new features are supported