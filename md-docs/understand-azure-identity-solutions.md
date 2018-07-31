# Understand Azure identity solutions
[MsDocs](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/understand-azure-identity-solutions)

## Terms to know & Concepts to understand

* Azure AD Directory 
  - Azure Subscription
  - Users, U.Groups & Apps
  - Tenant: single & multi
* **Multiple subscriptions can trust the same Azure AD directory, but a subscription will only trust a single Azure AD directory**
* Sometimes see the terms tenant, Azure AD, and Azure AD directory used interchangeably
* **Custom Domain**: alice@contoso.com instead of alice@contoso.onmicrosoft.com.
* Azure AD account
* Azure subscription administrator: can see the Account Center
* Azure AD **Global administrator**: full access to all Azure AD administrative features
* **Microsoft account**: created by you for personal use
* Work or school accounts: issued by an admin for business/academic use
* Azure Role-Based Access Control (**RBAC**): owner, contributor, reader & customs.
* Hybrid identity with Azure AD Connect between Windows Server AD DS and Azure AD.

## The difference between Windows Server AD DS and Azure AD

### OnPremise AD
* AD DS is a server role on Windows Server
* hierarchical structure based on X.500
* DNS for locating objects
* interacted with using LDAP
* uses Kerberos for authentication
* enables organizational units (OUs) and Group Policy Objects (GPOs) 
* trusts are created between domains

### Azure AD
* Users and groups are created in a flat structure without OUs or GPOs
* Authentication via SAML, WS-Federation, and OAuth
* Query using RestAPI instead of LDAP
  
## Extend Office 365 management and security capabilities
[eBook using Azure AD identity management with Office 365](https://info.microsoft.com/Extend-Office-365-security-with-EMS.html)

## Microsoft Azure identity solutions

### Do-it-yourself (DIY) AD DS
* For companies that need only a **small footprint** in the cloud
* deployment as virtual machines (VMs) on Azure
* relatively low-cost substitute to otherwise costly disaster recovery sites 
* Finally, you might need to deploy an application on Azure, **such as SharePoint**, that requires Windows Server AD DS, but has no dependency on the on-premises network or the corporate Windows Server Active Directory

### Azure AD
* Fully cloud-based Identity and access management as a Service (IDaaS) solution
* 3 editions: Free, Basic, and Premium

### Hybrid identity
* Extending on-premises directories to the cloud

### Azure AD Domain Services
* not meant to lift and shift your on-premises AD DS infrastructure to Azure VMs managed by Azure AD Domain Services

## Common scenarios and recommendations

* few virtual machines in Azure  
  --> **DIY AD DS**
* born in the cloud   
  --> **Azure AD**
* large investments in on-premises Windows Server Active Directory  
  --> **Hybrid**
* lightweight Azure VM meet on-premises requirements for dev and testing  
  --> **Azure AD Domain Services**

The End





