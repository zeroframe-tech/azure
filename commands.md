
---
layout:default
title:CommandReference
---
#CommandReference



1.AzureAccount&amp;SubscriptionManagement	
|Command|Description|Example|
|---------|-------------|---------|	
azlogin|LogintoAzure|azlogin	
azlogout|LogoutfromAzure|azlogout	
azaccountlist|Listallsubscriptions|azaccountlist--outputtable|	
azaccountset|Setactivesubscription|azaccountset--subscription"MySubscription"	
azaccountshow|Showcurrentsubscriptiondetailsazaccountshow	
	
2.ResourceGroupManagement|	
|Command|Description|Example|
|---------|-------------|---------|	
azgroupcreate|Createaresourcegroup|azgroupcreate--nameMyRG--locationeastus	
azgrouplist|Listallresourcegroups|azgrouplist--outputtable|	
azgroupdelete|Deletearesourcegroup|azgroupdelete--nameMyRG--yes|	
azgroupshow|Showdetailsofaresourcegroupazgroupshow--nameMyRG|	
	
3.VMCpmmand	
|Command|Description|Example|
|---------|-------------|---------|	
azvmcreate|CreateaVM|azvmcreate--resource-groupMyRG--nameMyVM--imageUbuntuLTS--admin-usernameazureuser--generate-ssh-keys|	
azvmlist|ListallVMs|azvmlist--outputtable|	
azvmstart|StartaVM|azvmstart--resource-groupMyRG--nameMyVM	
azvmstop|StopaVM|azvmstop--resource-groupMyRG--nameMyVM	
azvmdeallocate|DeallocateaVM(stop&amp;releaseresources)azvmdeallocate--resource-groupMyRG--nameMyVM	
azvmrestart|RestartaVM|azvmrestart--resource-groupMyRG--nameMyVM	
azvmdelete|DeleteaVM|azvmdelete--resource-groupMyRG--nameMyVM--yes	
azvmshow|GetVMdetails|azvmshow--resource-groupMyRG--nameMyVM	
	
4.StorageAccount&amp;BlobStorage|	
|Command|Description|Example|
|---------|-------------|---------|	
azstorageaccountcreateCreateastorageaccount|azstorageaccountcreate--namemystorageacc--resource-groupMyRG--locationeastus--skuStandard_LRS	
azstorageaccountlistListstorageaccounts|azstorageaccountlist--resource-groupMyRG--outputtable	
azstoragecontainercreateCreateablobcontainer|azstoragecontainercreate--account-namemystorageacc--namemycontainer|	
azstorageblobuploadUploadafiletoblobstorageazstorageblobupload--account-namemystorageacc--container-namemycontainer--namemyfile.txt--file./local-file.txt|
azstorageblobdownloadDownloadablob|azstorageblobdownload--account-namemystorageacc--container-namemycontainer--namemyfile.txt--file./downloaded-file.txt|	
	
5.Networking(VNet,NSG,PublicIP,NIC)	
|Command|Description|Example|
|---------|-------------|---------|

aznetworkvnetcreateCreateavirtualnetwork(VNet)aznetworkvnetcreate--resource-groupMyRG--nameMyVnet--address-prefix10.0.0.0/16--subnet-nameMySubnet--subnet-prefix10.0.0.0/24	
aznetworknsgcreateCreateaNetworkSecurityGroup(NSG)aznetworknsgcreate--resource-groupMyRG--nameMyNSG	
aznetworkpublic-ipcreateCreateapublicIP|aznetworkpublic-ipcreate--resource-groupMyRG--nameMyPublicIP--allocation-methodDynamic	
aznetworkniccreateCreateanetworkinterface(NIC)aznetworkniccreate--resource-groupMyRG--nameMyNIC--vnet-nameMyVnet--subnetMySubnet--network-security-groupMyNSG|	
	
6.AzureKubernetesService(AKS)|	
|Command|Description|Example|
|---------|-------------|---------|	
azakscreate|CreateanAKScluster|azakscreate--resource-groupMyRG--nameMyAKSCluster--node-count3--generate-ssh-keys	
azaksget-credentialsGetkubectlcredentials|azaksget-credentials--resource-groupMyRG--nameMyAKSCluster	
azaksscale|ScaleAKSnodes|azaksscale--resource-groupMyRG--nameMyAKSCluster--node-count5|	
azaksdelete|DeleteanAKScluster|azaksdelete--resource-groupMyRG--nameMyAKSCluster--yes	
	
7.AzureSQLDatabase	
|Command|Description|Example|
|---------|-------------|---------|	
azsqlservercreateCreateaSQLServer|azsqlservercreate--resource-groupMyRG--namemysqlserver--admin-usersqladmin--admin-passwordP@ssw0rd123--locationeastus|
azsqldbcreate|CreateaSQLDatabase|azsqldbcreate--resource-groupMyRG--servermysqlserver--namemydatabase--service-objectiveS0	
azsqldblist|Listalldatabases|azsqldblist--resource-groupMyRG--servermysqlserver	
azsqldbdelete|Deleteadatabase|azsqldbdelete--resource-groupMyRG--servermysqlserver--namemydatabase--yes|	
	
8.AzureWebApps(AppService)|	
|Command|Description|Example|
|---------|-------------|---------|	
azwebappcreate|Createawebapp|azwebappcreate--resource-groupMyRG--planMyAppServicePlan--nameMyWebApp--runtime"DOTNETCORE	
azwebapplist|Listallwebapps|azwebapplist--resource-groupMyRG--outputtable	
azwebappdeploymentsourceconfigConnecttoGitHub|azwebappdeploymentsourceconfig--resource-groupMyRG--nameMyWebApp--repo-urlhttps://github.com/user/repo.git--branchmaster--manual-integration	
azwebappdelete|Deleteawebapp|azwebappdelete--resource-groupMyRG--nameMyWebApp	
	
9.AzureCosmosDB	
|Command|Description|Example|
|---------|-------------|---------|	
azcosmosdbcreate|CreateaCosmosDBaccountazcosmosdbcreate--namemycosmosdb--resource-groupMyRG--kindMongoDB|	
azcosmosdbdatabasecreateCreateadatabase|azcosmosdbdatabasecreate--namemycosmosdb--resource-groupMyRG--db-namemydb|	
azcosmosdbcollectioncreateCreateacollection|azcosmosdbcollectioncreate--namemycosmosdb--resource-groupMyRG--db-namemydb--collection-namemycollection|	
	
10.AzureMonitoring&amp;Logs|	
|Command|Description|Example|
|---------|-------------|---------|	
azmonitoractivity-loglistViewactivitylogs|azmonitoractivity-loglist--resource-groupMyRG--outputtable|	
azmonitormetricslistGetVMmetrics|azmonitormetricslist--resource/subscriptions/{sub-id}/resourceGroups/MyRG/providers/Microsoft.Compute/virtualMachines/MyVM--metric"PercentageCPU"	
	
Formatoutputasatable:Use--outputtable	
FilterJSONoutput:Use--query(e.g.,--query"[].{Name:name,Location:location}")
Cpmmand	
Gethelp:Append--help(e.g.,azvmcreate--help)
