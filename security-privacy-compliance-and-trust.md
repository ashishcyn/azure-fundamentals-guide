## Security Privacy Compliance and Trust

### Securing network connectivity

• __Defense in depth__  
    Defense in depth is a **strategy** that employs a series of mechanisms __to slow__ the advance of an attack aimed at acquiring unauthorized access to data.The objective of defense in depth is to protect and prevent information from being stolen by individuals not authorized to access it. The common principles used to define a security posture are confidentiality, integrity, and availability, known collectively as CIA.Defense in depth can be visualized as a set of **layers**, with the Data to be secured at the center. Each layer provides protection so that if one layer is breached, a subsequent layer is already in place to prevent further exposure.  
    
    1. Physical security is the first line of defense to protect computing hardware in the datacenter.  
    2. Identity & access controls access to infrastructure and change control.  
    3.Perimeter layer uses distributed denial-of-service (DDoS) protection to filter large-scale attacks before they can cause a denial of service for end users.  
    4.Networking layer limits communication between resources through segmentation and access controls.  
    5.Compute layer secures access to virtual machines.  
    6.Application layer ensures applications are secure and free of vulnerabilities.  
    7.Data
    
• __Shared security__     
    As computing environments move from customer-controlled datacenters to cloud datacenters, the responsibility of security also shifts. Security is now a concern shared by both cloud providers and customers.
    
• __Azure Firewall__      
    [A Firewall](https://azure.microsoft.com/en-us/services/azure-firewall/) is a service that grants __server access__ based on the __originating IP__ address of each request. You create firewall rules that specify ranges of IP addresses. Only clients from these granted IP addresses will be allowed to access the server. Firewall rules also include specific network protocol and port information.  
    Azure Application Gateway also provides a firewall, called the __Web Application Firewall (WAF)__. WAF provides centralized, inbound protection for your web applications against common exploits and vulnerabilities.    
                
• __Azure DDoS Protection__ 
    DDoS(Distributed Denial of Service ) attacks attempt to __overwhelm and exhaust an application’s resources__, making the application __slow or unresponsive to legitimate users__. DDoS attacks can be targeted at any endpoint that is publicly reachable through the internet.Thus, any resource exposed to the internet, such as a website, is potentially at risk from a DDoS attack.  
    [Azure DDoS Protection](https://azure.microsoft.com/en-us/services/ddos-protection/ ) provides the following service tiers:    
    1. Basic    
    2. Standard    
    
DDoS standard protection can mitigate the following types of attacks:-  
        1. Volumetric attacks. The attack's goal is to flood the network layer with a substantial amount of seemingly legitimate traffic.  
        2. Protocol attacks. These attacks render a target inaccessible, by exploiting a weakness in the layer 3 and layer 4 protocol stack.  
        3. Resource (application) layer attacks. These attacks target web application packets to disrupt the transmission of data between hosts  
        
• __NSG__   
    [Network Security Groups](https://docs.microsoft.com/en-us/azure/virtual-network/security-overview#network-security-groups) allow you to __filter network traffic__ to and from Azure resources in an Azure virtual network.   
    An NSG can contain multiple inbound and outbound security __rules__ that enable you to filter traffic to and from resources by source and destination IP address, port, and protocol.  
• __ASG__    
    [Application security groups](https://docs.microsoft.com/en-us/azure/virtual-network/security-overview#application-security-groups) enable you to configure network security as a natural extension of an application's structure, allowing you to group virtual machines and define network security policies based on those groups.An ASG enables you to group __servers with similar port filtering requirements__, and group together servers with similar functions, such as web servers. 
    
    
   ### Core Azure Identity services    

• __Authentication and authorization__   
    Authentication:- is the process of establishing the identity of a person or service looking to access a resource.   
    It involves the act of challenging a party for legitimate credentials and provides the basis for creating a security principal for identity and access control use.It establishes if they are who they say they are  
    Authorization:- Authorization is the process of establishing what level of access an authenticated person or service has. 
    It specifies what data they're allowed to access and what they can do with it.  
• __Azure Active Directory
    [Azure AD](https://azure.microsoft.com/en-us/services/active-directory/)  
• __Azure Multi-Factor Authentication__
    [AMFA](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-mfa-howitworks)  


### Security tools and features

• __Azure Security Center__
    [Azure Security Center](https://azure.microsoft.com/en-us/services/security-center/) is a __monitoring service__ that provides __threat protection__ across all of your services both in __Azure__, and __on-premises__.  
    Azure Security Center is available in two tiers:  
    1)Free:- Available as part of your Azure subscription, this tier is limited to assessments and recommendations of Azure resources only.   
    2)Standard:- This tier provides a full suite of security-related services including continuous monitoring, threat detection, just-in-time access control for ports, and more.   
    
• __Key Vault__  
    [Azure Key Vault](https://azure.microsoft.com/en-us/services/key-vault/) is a centralized cloud service for storing your applications' secrets.Key Vault helps you control your applications' secrets by keeping them in a single, central location and by providing secure access, permissions control, and access logging capabilities  
    
• __Azure Information Protection__  
    [AIP](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)  
    
• __Azure Advanced Threat Protection__  : 
    [ATP](https://azure.microsoft.com/en-us/features/azure-advanced-threat-protection/)  
    Azure Advanced Threat Protection is a cloud-based security solution that identifies, detects, and helps you investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.Azure ATP is capable of detecting known malicious attacks and techniques, security issues, and risks against your network.  
    


### Azure Governance methodologies

• __Azure Policy__
    [Azure Policy](https://azure.microsoft.com/en-us/services/azure-policy/) is a __service__ in Azure that you use to create, assign, and, manage policies.These policies enforce different __rules__ and effects over your resources, so those resources stay compliant with your corporate standards and service-level agreements (SLAs).  
    
• __Policy Initiatives__  
    Policy Initiatives work with Azure Policies.    
    Initiative definitions:- An initiative definition is a set of policy definitions to help track your compliance state for a larger goal. Initiative assignments reduce the need to make several initiative definitions for each scope.  
    Initiative assignment:-  Like a policy assignment, an initiative assignment is an initiative definition assigned to a specific scope. Initiative assignments reduce the need to make several initiative definitions for each scope  
    
• __Role-Based Access Control (RBAC)__  
    
• __Resource locks__    
    [Resource Locks](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources ) help you prevent accidental deletion or modification of your Azure resources.You can manage these locks from within the Azure portal. To view, add, or delete locks, go to the SETTINGS section of any resource's settings blade.    
    
• __Azure Blueprints__ 
    [Azure Blueprints](https://azure.microsoft.com/en-us/services/blueprints/) enable cloud architects to define a repeatable set of Azure resources that implement and adhere to an organization's standards, patterns, and requirements  
    
• __Subscription governance__ 


### Monitoring and reporting options in Azure

• __Tags__  
    1.You apply [tags](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources) to your Azure resources giving metadata to logically organize them into a taxonomy  
    2.Each tag consists of a name and a value pair  
    3.For example, you can apply the name Environment and the value Production to all the resources in production, or tag by company departments. For example, the name of Department with a value of IT.  
    
• __Azure Monitor__      
	1.[Azure Monitor maximizes](https://azure.microsoft.com/en-us/services/monitor/) the availability and performance of your applications by delivering a comprehensive solution for collecting, analyzing, and acting on telemetry from your cloud and on-premises environments.   
	2.It helps you understand how your applications are performing and proactively identifies issues affecting them and the resources they depend on.   
    
• __Azure Health Service__   
    Azure Service Health(https://azure.microsoft.com/en-us/features/service-health/) is a suite of experiences that provide __personalized guidance and support__ when issues with Azure services affect you. 
    It can __notify__ you, help you __understand__ the impact of issues, and keep you updated as the issue is __resolved__. Azure Service Health can also help you __prepare__ for planned maintenance and changes that could affect the availability of your resource  
    Azure Service Health is composed of:-  
    1. Azure Status- provides a global view of the __health state__ of Azure services     
    2. Service Health - provides you with a __customizable dashboard__ that tracks the state of your Azure services in the regions where you use them    
    3. Resource Health - helps you diagnose and obtain support when an Azure service issue __affects__ your resources    
    
• __Monitoring applications and services__ 
    Data monitoring is only useful if it improves your visibility of the operations in your computing environment.   
    Azure Monitor includes several features and tools that provide valuable insights into your applications, and the other resources they may depend on. 
    Azure Monitor features can be organized into four categories. Analyze, Respond, Visualize and Integrate.  
    1.Analyze:-  
         a)Application Insights - monitors the availability, performance, and usage of your web applications   
         b)Azure Monitor for containers -designed to monitor the performance of container workloads, which are deployed to managed Kubernetes clusters hosted on Azure Kubernetes Service (AKS).    
         c)Azure Monitor for VMs          
    2.Respond:-  
         a)Alerts  
         b)Autoscale         
    3.Visualize:-  
    4.Integrate:-  
    
    

### Privacy, compliance and data protection standards in Azure

•   When selecting a cloud provider to host our solutions, we should understand how that provider can help us comply with [regulations and standards](https://docs.microsoft.com/en-us/microsoft-365/compliance/offering-home)   
•   1.CJIS  
•   2.CSA STAR Certification.  
•   3.__General Data Protection Regulation (GDPR)__:-As of May 25, 2018, a European privacy law—GDPR—is in effect  
•   4.EU Model Clauses  
•   5.HIPAA  
•   6.__ISO/IEC 27018__:- Microsoft is the first cloud provider to have adopted the ISO/IEC 27018 code of practice, covering the processing of personal information by cloud service providers  
•   7.Multi-Tier Cloud Security (MTCS) Singapore  
•   8.Service Organization Controls (SOC) 1, 2, and 3  
•   9.__National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF)__:-NSIT CSF is a voluntary Framework that consists of standards, guidelines, and best practices to manage cybersecurity-related risks  
•   10.UK Government G-Clouz:-The UK Government G-Cloud is a cloud computing certification for services used by government entities in the United Kingdom  

    
• __Microsoft Privacy Statement__ 
    [The Microsoft privacy statement](https://privacy.microsoft.com/en-us/privacystatement) explains __what personal data__ Microsoft processes, __how__ Microsoft processes it, and for __what__ purposes.   
    
• __Trust Center__   
    [The Trust Center](https://www.microsoft.com/en-us/trust-center) is a website resource containing information and details about __how Microsoft implements and supports__ security, privacy, compliance, and transparency in all Microsoft cloud products and services.  
    
• __Service Trust Portal__
    [The Service Trust Portal (STP)](https://servicetrust.microsoft.com/) hosts the Compliance Manager service, and is the Microsoft public site for publishing __audit reports__ and other __compliance-related information__ relevant to Microsoft’s cloud services.  
    
• __Compliance Manager__    
     [Compliance Manager](https://docs.microsoft.com/en-us/microsoft-365/compliance/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud) is a __workflow-based risk assessment dashboard__ within the Trust Portal that enables you to track, assign, and verify your organization's regulatory compliance activities related to Microsoft professional services and Microsoft cloud services such as Office 365, Dynamics 365, and Azure.  
    
• __Azure Government services__  
     1)[Azure Government](https://docs.microsoft.com/en-us/azure/azure-government/documentation-government-welcome) is a __separate instance__ of the Microsoft Azure service.    
	 2)It addresses the security and compliance needs of US federal agencies, state and local governments, and their solution providers.   
	 3)Azure Government offers __physical isolation__ from non-US government deployments and provides screened US personnel.  
    
• __Azure China__ 
    [Azure China](https://docs.microsoft.com/en-us/azure/china/) is operated by 21Vianet (Azure China 21Vianet) is a __physically separated instance__ of cloud services __located in China__, independently operated and transacted by Shanghai Blue Cloud Technology Co., Ltd. (“21Vianet”), a wholly owned subsidiary of Beijing 21Vianet Broadband Data Center Co. Ltd.  





