# :cloud: Enum_AzureSubdomains:

A Metasploit module for enumerating public Azure services, ```enum_azuresubdomains.rb``` will check for valid Azure subdomains via various DNS queries. This reconnaissance and enumeration module rapidly identifies API services, storage accounts, key vaults, databases, and more! Expedite your cloud recon with this handy auxiliary module.


<p align="center">
  <img alt="AzureDoggo" src="https://user-images.githubusercontent.com/72598486/216847358-a72ce9e8-7d25-4b27-b386-f21d339580fa.png">
</p>

# Anonymously Enumerating Azure Services:

Microsoft makes use of a number of different domains/subdomains for each of their Azure services. From SQL databases to email and SharePoint drives, each service maps to its respective domain/subdomain, and I have included a list of Azure-related domains below:

| Domain | Associated Service |
| --- | --- |
| azurewebsites.net | App Services |
| scm.azurewebsites.net | App Services - Management |
| p.azurewebsites.net | App Services |
| cloudapp.net | App Services |
| file.core.windows.net | Storage Accounts-Files |
| blob.core.windows.net | Storage Accounts-Blobs |
| queue.core.windows.net | Storage Accounts-Queues |
| table.core.windows.net | Storage Accounts-Tables |
| redis.cache.windows.net | Databases-Redis |
| documents.azure.com | Databases-Cosmos DB |
| database.windows.net | Databases-MSSQL |
| vault.azure.net | Key Vaults |
| onmicrosoft.com | Microsoft Hosted Domain |
| mail.protection.outlook.com | Email |
| sharepoint.com | SharePoint |
| azureedge.net | CDN |
| search.windows.net | Search Appliance |
| azure-api.net | API Services |

It may take a while to pay off, but enumerating existing Azure subdomains may be handy for anyone looking to do subdomain takeovers. Subdomain takeovers are usually done the other way around (finding a domain that’s no longer registered/in use), but by finding the domains now, and keeping tabs on them for later, you may be able to monitor for potential subdomain takeovers.

# Demo:

https://user-images.githubusercontent.com/72598486/216848983-6dd880dd-9549-4a39-8bf8-476a870239c4.mp4


# Install:

Download repository:

```
$ mkdir Enum_Azure
$ cd Enum_Azure/
$ sudo git clone https://github.com/RoseSecurity/Enum_AzureSubdomains.git
```

Usage:

To load the script into Metasploit:

```
# Create directory for module
$ mkdir -p ~/.msf4/modules/auxiliary/gather
# Move script into folder
$ mv enum_azuresubdomains.rb ~/.msf4/modules/auxiliary/gather
```

Fire up Metasploit:

```
$ msfconsole -q
# Reload modules
msf> reload_all
msf> use /modules/auxiliary/gather/enum_azuresubdomains
```

If you encounter any errors, check the following log:

```
$ tail ~/.msf4/logs/framework.log
```
