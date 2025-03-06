## Test Repo for expirementing with Terraform's VC Workflow
\
\
**High Level Prerequisites**
- Create Github Repo and add Terraform files to create a simple and free resource (eg Resource group).
- Create Azure Account, a Subscription and a Service Principal ([Instructions](https://learn.microsoft.com/en-us/azure/developer/terraform/authenticate-to-azure-with-service-principle?tabs=azure-powershell)). In simple terms this is an account that will be used by Terraform to make changes in Azure. Personally I used Azure cloud shell since no setup is needed compared to configuring my desktops powershell.
- Create Terraform Workspace and connect it to Github Repo through version control settings.
- In Terraform Workspace, declare the following ***sensitive*** workspace variables that are being retrieved from Azure:
    - ARM_CLIENT_ID
    - ARM_CLIENT_SECRET
    - ARM_SUBSCRIPTION_ID
    - ARM_TENANT_ID
- Per Terraform's [documentation](https://developer.hashicorp.com/terraform/cloud-docs/run/ui): 
    at least one run must be manually queued to confirm that the workspace is ready for further runs. This will also help to ensure if the connection between Terraform and Azure is working.

- Commit one change to check if the Version Control Workflow is working. With the settings I set in Terraform cloud, I have to accept the plan before Terraform applies it.
