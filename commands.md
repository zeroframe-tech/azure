# Azure CLI Command Reference

 1. Azure Account & Subscription Management

| Command | Description | Example |
|---------|-------------|---------|
| az login | Log in to Azure | az login |
| az logout | Log out from Azure | az logout |
| az account list | List all subscriptions | az account list --output table |
| az account set | Set active subscription | az account set --subscription "My Subscription" |
| az account show | Show current subscription details | az account show |

 2. Resource Group Management

| Command | Description | Example |
|---------|-------------|---------|
| az group create | Create a resource group | az group create --name MyRG --location eastus |
| az group list | List all resource groups | az group list --output table |
| az group delete | Delete a resource group | az group delete --name MyRG --yes |
| az group show | Show details of a resource group | az group show --name MyRG |

 3. Virtual Machine Commands

| Command | Description | Example |
|---------|-------------|---------|
| az vm create | Create a VM | az vm create --resource-group MyRG --name MyVM --image UbuntuLTS --admin-username azureuser --generate-ssh-keys |
| az vm list | List all VMs | az vm list --output table |
| az vm start | Start a VM | az vm start --resource-group MyRG --name MyVM |
| az vm stop | Stop a VM | az vm stop --resource-group MyRG --name MyVM |
| az vm deallocate | Deallocate a VM | az vm deallocate --resource-group MyRG --name MyVM |
| az vm restart | Restart a VM | az vm restart --resource-group MyRG --name MyVM |
| az vm delete | Delete a VM | az vm delete --resource-group MyRG --name MyVM --yes |
| az vm show | Get VM details | az vm show --resource-group MyRG --name MyVM |

 4. Storage Account & Blob Storage

| Command | Description | Example |
|---------|-------------|---------|
| az storage account create | Create storage account | az storage account create --name mystorageacc --resource-group MyRG --location eastus --sku Standard_LRS |
| az storage account list | List storage accounts | az storage account list --resource-group MyRG --output table |
| az storage container create | Create blob container | az storage container create --account-name mystorageacc --name mycontainer |
| az storage blob upload | Upload to blob storage | az storage blob upload --account-name mystorageacc --container-name mycontainer --name myfile.txt --file ./local-file.txt |
| az storage blob download | Download a blob | az storage blob download --account-name mystorageacc --container-name mycontainer --name myfile.txt --file ./downloaded-file.txt |

 5. Networking (VNet, NSG, Public IP, NIC)

| Command | Description | Example |
|---------|-------------|---------|
| az network vnet create | Create virtual network | az network vnet create --resource-group MyRG --name MyVnet --address-prefix 10.0.0.0/16 --subnet-name MySubnet --subnet-prefix 10.0.0.0/24 |
| az network nsg create | Create NSG | az network nsg create --resource-group MyRG --name MyNSG |
| az network public-ip create | Create public IP | az network public-ip create --resource-group MyRG --name MyPublicIP --allocation-method Dynamic |
| az network nic create | Create NIC | az network nic create --resource-group MyRG --name MyNIC --vnet-name MyVnet --subnet MySubnet --network-security-group MyNSG |

 6. Azure Kubernetes Service (AKS)

| Command | Description | Example |
|---------|-------------|---------|
| az aks create | Create AKS cluster | az aks create --resource-group MyRG --name MyAKSCluster --node-count 3 --generate-ssh-keys |
| az aks get-credentials | Get kubectl credentials | az aks get-credentials --resource-group MyRG --name MyAKSCluster |
| az aks scale | Scale AKS nodes | az aks scale --resource-group MyRG --name MyAKSCluster --node-count 5 |
| az aks delete | Delete AKS cluster | az aks delete --resource-group MyRG --name MyAKSCluster --yes |

 7. Azure SQL Database

| Command | Description | Example |
|---------|-------------|---------|
| az sql server create | Create SQL Server | az sql server create --resource-group MyRG --name mysqlserver --admin-user sqladmin --admin-password P@ssw0rd123 --location eastus |
| az sql db create | Create SQL Database | az sql db create --resource-group MyRG --server mysqlserver --name mydatabase --service-objective S0 |
| az sql db list | List databases | az sql db list --resource-group MyRG --server mysqlserver |
| az sql db delete | Delete database | az sql db delete --resource-group MyRG --server mysqlserver --name mydatabase --yes |

 8. Azure Web Apps (App Service)

| Command | Description | Example |
|---------|-------------|---------|
| az webapp create | Create web app | az webapp create --resource-group MyRG --plan MyAppServicePlan --name MyWebApp --runtime "DOTNETCORE" |
| az webapp list | List web apps | az webapp list --resource-group MyRG --output table |
| az webapp deployment source config | Connect to GitHub | az webapp deployment source config --resource-group MyRG --name MyWebApp --repo-url https://github.com/user/repo.git --branch master --manual-integration |
| az webapp delete | Delete web app | az webapp delete --resource-group MyRG --name MyWebApp |

 9. Azure Cosmos DB

| Command | Description | Example |
|---------|-------------|---------|
| az cosmosdb create | Create Cosmos DB account | az cosmosdb create --name mycosmosdb --resource-group MyRG --kind MongoDB |
| az cosmosdb database create | Create database | az cosmosdb database create --name mycosmosdb --resource-group MyRG --db-name mydb |
| az cosmosdb collection create | Create collection | az cosmosdb collection create --name mycosmosdb --resource-group MyRG --db-name mydb --collection-name mycollection |

 10. Azure Monitoring & Logs

| Command | Description | Example |
|---------|-------------|---------|
| az monitor activity-log list | View activity logs | az monitor activity-log list --resource-group MyRG --output table |
| az monitor metrics list | Get VM metrics | az monitor metrics list --resource /subscriptions/{sub-id}/resourceGroups/MyRG/providers/Microsoft.Compute/virtualMachines/MyVM --metric "Percentage CPU" |

 Usage Tips

- Format output as table: Append --output table  
- Filter JSON output: Use --query (e.g., --query "[].{Name:name, Location:location}")  
- Get help: Append --help (e.g., az vm create --help)