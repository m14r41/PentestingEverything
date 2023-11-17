## Some Awesome List 

|S.N    | Credit    | Resources Link |
| -------- | ------- |------- |
| 1        | Payload All The thins  | https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Cloud%20-%20Azure%20Pentest.md   |
| 2         | HackTheTriks|  https://cloud.hacktricks.xyz/pentesting-cloud/azure-security |



# AZURE-SPECIFIC PENTESTING CHECKLIST

## **Azure Configuration Assessment**

### **1. Azure Resource Enumeration**
   - Enumerate Azure resources using Azure Portal, Azure PowerShell, or Azure CLI.
   - Tools: Azure Portal, Azure PowerShell, Azure CLI
   - Command: `az resource list`

### **2. Storage Account Security**
   - Check for misconfigured Azure Storage accounts with public access.
   - Verify that storage account access keys and shared access signatures (SAS) are securely managed.
   - Tools: Azure Storage Explorer, Azure CLI
   - Command (Azure CLI): `az storage account list`

### **3. Azure AD Enumeration**
   - Enumerate Azure Active Directory (Azure AD) users, groups, and roles.
   - Identify guest users and their permissions.
   - Tools: Azure Portal, Azure PowerShell
   - Command (Azure PowerShell): `Get-AzureADUser`

### **4. Azure Functions and Logic Apps**
   - Assess Azure Functions and Logic Apps for potential security misconfigurations and vulnerabilities.
   - Check for insecure Azure Functions deployments.
   - Tools: Azure Functions Portal, Azure CLI
   - Command (Azure CLI): `az functionapp list`

## **Network Security Assessment**

### **5. Virtual Network Security**
   - Review virtual network configurations, subnets, and network security groups (NSGs).
   - Identify potential NSG misconfigurations.
   - Tools: Azure Portal, Azure PowerShell, Azure CLI
   - Command (Azure CLI): `az network nsg list`

### **6. Azure Firewall and Network Security Groups**
   - Analyze Azure Firewall and NSG rules for vulnerabilities and misconfigurations.
   - Verify proper network segmentation.
   - Tools: Azure Portal, Azure PowerShell, Azure CLI
   - Command (Azure CLI): `az network firewall list`

### **7. VPN and ExpressRoute**
   - Assess VPN and ExpressRoute configurations for security.
   - Verify encryption and authentication settings.
   - Tools: Azure Portal, Azure PowerShell, Azure CLI
   - Command (Azure CLI): `az network vpn-site list`

## **Azure Service Security Assessment**

### **8. Virtual Machine Security**
   - Review VM configurations, including OS security settings and patch management.
   - Check for exposed RDP/SSH ports.
   - Tools: Azure Portal, Azure PowerShell, Azure CLI
   - Command (Azure CLI): `az vm list`

### **9. Azure App Service Security**
   - Analyze the security of web apps hosted on Azure App Service.
   - Check for vulnerabilities like SQL injection and insecure configurations.
   - Tools: Azure Portal, Web Application Scanning Tools
   - Command (Scanning): Varies by tool

### **10. Azure SQL Database Security**
   - Assess the security settings and configurations of Azure SQL Database instances.
   - Verify proper data encryption and firewall rules.
   - Tools: Azure Portal, Azure PowerShell, Azure CLI
   - Command (Azure CLI): `az sql server list`

## **Identity and Access Management**

### **11. Azure AD Security**
   - Review Azure AD security settings, identity policies, and password policies.
   - Check for exposed Azure AD endpoints.
   - Tools: Azure Portal, Azure PowerShell
   - Command (Azure PowerShell): `Get-AzureADPolicy`

### **12. Privileged Identity Management (PIM)**
   - Review Azure AD PIM settings and identify privileged roles.
   - Check for overprivileged accounts and monitor PIM activities.
   - Tools: Azure Portal, Azure PowerShell
   - Command (Azure PowerShell): `Get-AzureADMSPrivilegedRoleAssignment`

## **Security and Compliance**

### **13. Azure Security Center**
   - Analyze Azure Security Center recommendations and compliance settings.
   - Verify resource security health.
   - Tools: Azure Security Center, Azure Portal
   - Command: Varies by tool

### **14. Logging and Auditing**
   - Ensure Azure Monitor and Azure Sentinel are properly configured for log collection.
   - Review logs for security incidents and suspicious activities.
   - Tools: Azure Monitor, Azure Sentinel, Log Analytics
   - Command: Varies by tool

## **Vulnerability Assessment**

### **15. Automated Scanning**
   - Perform automated vulnerability scanning using Azure Security Center or third-party tools.
   - Check for vulnerabilities specific to Azure services.
   - Tools: Azure Security Center, Third-party Scanners
   - Command: Varies by tool

