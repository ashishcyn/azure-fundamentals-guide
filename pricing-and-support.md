## Pricing and Support

### Azure Subscriptions

• Using an Azure account requires an Azure subscription which provides you with authenticated and authorized access to Azure products and services and allows you to provision resources.   
• `An Azure subscription` is a logical unit of Azure services that links to an Azure account, which is an identity in Azure Active Directory (Azure AD) or in a directory that an Azure AD trusts.    
• An account can have one subscription or multiple subscriptions that have different billing models and to which you apply different access-management policies   
• You can use Azure subscriptions to define boundaries around Azure products, services, and resources.   


• There are `two types` of subscription boundaries that you can use:-    
•  1. Billing boundary    
•  2. Access control boundary   

• Subscription `options`:-  
•  1. A free account [click here to create](https://azure.microsoft.com/en-us/free/)  
•  2. Pay-As-You-Go  
•  3. Member offers  
  
  
• `Management Groups`: The organizing structure for resources in Azure has four levels: 1st Management groups, 2nd subscriptions, 3rd resource groups, and 4th resources.  
• `1.Management groups:` These are containers that help you manage access, policy, and compliance for multiple subscriptions.All subscriptions in a management group automatically inherit the conditions applied to the management group  
• `2.Subscriptions:` - A subscription, groups together user accounts and the resources that have been created by those user accounts  
• `3.Resource group:`- A resource group is a logical container into which Azure resources like web apps, databases, and storage accounts are deployed and managed.  
• `4.Resources:` - Resources are instances of services that you create, like virtual machines, storage, or SQL databases.  



### Planing and managing the cost

• There are three main `customer types` on which the available purchasing options for Azure products and services.   
• 1.  Enterprise  
• 2.  Web direct  
• 3.  Cloud Solution Provider  

• `Factors affecting costs` : When you provision an Azure resource, Azure creates one or more meter(`Usage meters`) instances for that resource.   
• The meters track the resources' usage, and each meter generates a usage record that is used to calculate your bill  
• The main factors that affect Azure costs, including `resource type`, `services`, and the `user's location`.     

• `Zones` for billing purposes:Zone 1,Zone 2,Zone 3, DE Zone 1   
• `Pricing Calculator` is a tool that helps you estimate the cost of Azure products - [Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)  
• `Total Cost of Ownership Calculator`is a tool that you use to estimate cost savings you can realize by migrating to Azure [TCO](https://azure.microsoft.com/en-us/pricing/tco/)  

• `Minimizing costs:`   
• 1)Perform cost analyses  
• 2)Monitor usage with Azure Advisor  
• 3)Use spending limits  
• 4)Use Azure Reservations  
• 5)Choose low-cost locations and regions    
• 6)Research available cost-saving offers  
• 7)Apply tags to identify cost owners  

• `Azure Cost Management` is an Azure product that provides a set of tools for monitoring, allocating, and optimizing your Azure costs. [Cost-management](https://azure.microsoft.com/en-us/services/cost-management/)  
 

### Support options available

• [Support plans](https://azure.microsoft.com/en-us/support/plans/)  
• Basic  
• Developper  
• Standard  
• Professional Direct  

`BASIC:`- No Technical Support  
`DEVELOPER:`- Business hours access1 to Support Engineers via email  
`STANDARD, PROFESSIONAL DIRECT, PREMIER:`- 24x7 access to Support Engineers via email and phone  

### Azure Service Level Agreements (SLAs)

•	SLAs describe Microsoft's commitment to providing Azure customers with certain performance standards  
•	99%------DownTime-----3.65 days/year  
•	99.9%-------DT------8.76 hours/y  
•	99.95%------DT------4.38 hours/y  
•	99.99%------DT------52.56 minutes/y  
•	99.999%-----DT------5.26 minutes/y  


### Composite SLAs

•	When combining SLAs across different service offerings, the resultant SLA is a called a __Composite SLA__  
•	The resulting composite SLA can provide `higher or lower  uptime` values, depending on your application architecture.  
•	Web Apps (99.95%) connecting to SQL Database(99.99%)   [Combined -->99.95 % × 99.99 % = approx 99.94 %]  
•	you can improve the composite SLA by creating `independent fallback path`  
•	eg:
	if SQL Database is unavailable, you can put transactions into a `Queue` (99.%)for processing at a later time.  
•	Database *OR* Queue = 1.0 − (0.0001 × 0.001) = 99.99999%  
•	Therefore, the total composite SLA is Web app *AND* (Database *OR* Queue)= 99.95 % × 99.99999 % = ~ 99.95%

   
   
### Service lifecycle in Azure

• `Private Preview` means that an Azure feature is available to certain Azure customers for evaluation purposes.  
• `Public Preview`  means that an Azure feature is available to all Azure customers for evaluation purposes.   
• Once a feature is evaluated and tested successfully, it may be released to customers as part of Azure's default product, service or feature set  
• In other words, the feature may be made available for all Azure customers, and a feature released to all Azure customers typically goes to General Availability or `GA`.  
• How to `monitor feature updates and product changes` : Go to the [Azure updates page](https://azure.microsoft.com/en-us/updates/) for information about the latest updates to Azure products, services, and features, as well as product roadmaps and announcements.
