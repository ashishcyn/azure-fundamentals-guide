### Core Azure Services

-------------------------


### Core Azure architectural components 
**Region**
```
Microsoft Azure is made up of datacenters located around the globe.    
These datacenters are organized and made available to end users by region.   
A region is a geographical area on the planet containing at least one, but potentially multiple   
datacenters that are in close proximity and networked together with a low-latency network  
Azure is generally available in 54 regions and available in 140 countries  

For most Azure services, when you deploy a resource in Azure, you choose the region where you want your resource to be deployed.  
Some services or virtual machine features are only available in certain regions
There are also some global Azure services that do not require you to select a region(Microsoft Azure Active Directory, 
Microsoft Azure Traffic Manager, Azure DNS etc)  
``` 
**Region Pairs**
```
Each Azure region is paired with another region within the same geography, together making a region pair.  
Azure prefers at least 300 miles of separation between datacenters in a regional pair(Physical datacenter separation reduces the 
likelihood of natural disasters, civil unrest, power outages, or physical network outages affecting both regions at once)
```
**Geographies**
```
A geography is a discrete market typically containing two or more regions that preserves data residency and compliance boundaries.  
Geographies are broken up into Americas, Europe, Asia Pacific, Middle East and Africa.  
```
**Availability options**
```
A single virtual machine with premium storage has an SLA of 99.9%.   
You can quickly migrate existing virtual machines to Azure through “lift and shift”.  
By placing virtual machines in an _availability set_ you protect against datacenter failures and increases the SLA to 99.95%.(Protesting against failures withina data centers)  
Adding virtual machines to _availability zones_ protects from entire datacenter failures and increases the SLA to 99.99%.  
For multi-region disaster recovery region pairs protects and provides data residency boundaries.  
```
**Availability Sets**
```
Availability sets are a way for you to ensure your application remains online if a high-impact maintenance event is required, or a hardware a failure occurs.  
Availability sets are made up of Update domains (UD)(logical separation) and Fault domains (FD)(physical separation) with in a DataCenter  
```
**Availability Zones**
```
Availability zones are physically separate locations within an Azure region that use availability sets to provide additional fault tolerance.
```
**Resource Groups**
```
A resource group is a unit of management for your resources in Azure. You can think of your resource group as a   
container that allows you to aggregate and manage all the resources(Web,VM,DB,Storage etc ) required for your application in a single manageable unit.   
This allows you to manage the application collectively over its lifecycle, rather than manage components individually.  

You can manage and apply the following resources at resource group level:

* Metering and billing
* Policies
* Monitoring and alerts
* Quotas
* Access control  

Remember that when you delete a resource group you delete all resources contained within it.


* Each resource must exist in one, and only one, resource group.
* A resource group can contain resources that reside in different regions.
* You decide how you want to allocate resources to resource groups based on what makes the most sense for your organization.
* You can add or remove a resource to a resource group at any time.
* You can move a resource from one resource group to another.
* Resources for an application do not need to exist in the same resource group. However, it is recommended that you 
keep them in the same resource group for ease of management.
```
**Azure Resource Manager**
```
* Azure Resource Manager is a management layer in which resource groups and all the resources within it are 
created, configured, managed, and deleted. 
* It provides a consistent management layer which allows you automate the deployment and configuration of 
resources using different automation and scripting tools, such as Microsoft Azure PowerShell, Azure 
Command-Line Interface (Azure CLI), Azure portal, REST API, and client SDKs.

With Azure Resource Manager, you can
* Deploy Application resources
* Organize resources
* Control access and resources
```


-------------------------
### Core Azure services and products  

**Azure compute**  
```
* Azure compute is an on-demand computing service for running cloud-based applications.   
It provides computing resources such as disks, processors, memory, networking and operating systems.  

* The resources are available on-demand and can typically be made available in minutes or even seconds.  
You pay only for the resources you use and only for as long as you're using them.  

* There are many compute services two of the most common are: virtual machines and containers.
```

**Azure compute services** 
```
* Virtual machines, (VMs), are software emulations of physical computers. They include a virtual processor, memory, storage, and networking resources. They host an operating system, and you're able to install and run software just like a physical computer. When using a remote desktop client, you can use and control the virtual machine as if you were sitting in front it.

* Azure supports a wide range of computing solutions for development and testing, running applications, and extending your datacenter, including Linux, Windows Server, Microsoft SQL Server, Oracle, IBM, and SAP.
* Azure also has many services that can run virtual machines, each providing different options depending on your requirements. 
* Some of the most prominent services are VM Scale Sets, App Services, and Azure Functions.

1. Azure virtual machines(VM)

* Azure virtual machines lets you create and use virtual machines in the cloud. 
* It provides IaaS and can be used in a variety of different ways. 
* When you need total control over an operating system and environment, Azure VMs are an ideal choice. 
* Just like a physical computer, you're able to customize all the software running on the VM. 
* This is particularly helpful when you are running custom software or custom hosting configurations.

2. VM scale sets  
* Virtual machine scale sets are an Azure compute resource that you can use to deploy and manage a set of identical VMs. With all VMs configured the same, VM scale sets are designed to support true auto-scale—no pre-provisioning of VMs is required—and as such makes it easier to build large-scale services targeting big compute, big data, and containerized workloads. So, as demand goes up more virtual machine instances can be added, and as demand goes down virtual machines instances can be removed. The process can be manual, automated, or a combination of both.

3. App services  
* With App services, you can quickly build, deploy, and scale enterprise-grade web, mobile, and API apps running on any platform. You can meet rigorous performance, scalability, security and compliance requirements while using a fully managed platform to perform infrastructure maintenance. App Services is a platform as a service (PaaS) offering.

4. Functions  
* Azure Functions are ideal when you're concerned only about the code running your service and not the underlying platform or infrastructure. They're commonly used when you need to perform work in response to an event (often via a REST request), timer, or message from another Azure service, and when that work can be completed quickly, within seconds or less.

``` 

Walkthrough-Create a virtual machine  
https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/01-Create%20a%20virtual%20machine.md


**Container services**    
```
* Containers are a virtualization environment.
* Containers reference the operating system of the host environment that runs the container.
* Unlike virtual machines you do not manage the operating system.
* Containers are lightweight and are designed to be created, scaled out, and stopped dynamically.
* Containers allows you to respond to changes on demand and quickly restart in case of a crash or hardware interruption.
* Azure supports Docker containers.

* There are two ways to manage both Docker and Microsoft-based containers in Azure.
1.Azure Container Instances -ACI: 
  Azure Container Instances offers the fastest and simplest way to run a container in Azure without having to 
  manage any virtual machines or adopt any additional services. 
  It is a PaaS offering that allows you to upload your containers, which it will run for you.
  
2.Azure Kubernetes Service -AKS
  Azure Kubernetes Service (AKS) is a complete orchestration service for containers with distributed architectures and large volumes of containers. 
  Orchestration is the task of automating and managing a large number of containers and how they interact.	

```
Walkthrough-Deploy Azure Container Instances  
https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/02-Deploy%20Azure%20Container%20Instances.md

**Azure network services**  
```
* Azure Networking: Azure Networking allows you to connect cloud and on-premises infrastructure and services to provide your customers and users the best possible experience. 
  Once the resources move to Azure, they require the same networking functionality as an on-premises deployment. 
  In specific scenarios, they may require some level of network isolation. 
  Azure networking components offer a range of functionality and services that can help organizations design and build cloud infrastructure services that meet their requirements.
Some of the most common networking service types in Azure are:

1.Azure Virtual Network:
	* Azure Virtual Network enables many types of Azure resources such as Azure VMs to securely communicate with each other, the internet, and on-premises networks. 
	* A virtual network is scoped to a single region; however, multiple virtual networks from different regions can be connected using virtual network peering. 
	* With Azure Virtual Network you can provide isolation, segmentation, communication with on-premises and cloud resources, routing and filtering of network traffic.
2.Azure Load Balancer:
	* Azure Load Balancer can provide scale for your applications and create high availability for your services. 
	* Load Balancer supports inbound and outbound scenarios, provides low latency and high throughput, and scales up to millions of flows for all Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) applications. 
	* You can use Load Balancer with incoming internet traffic, internal traffic across Azure services, port forwarding for specific traffic, or outbound connectivity for VMs in your virtual network.
3.VPN gateway:
	* A VPN gateway is a specific type of virtual network gateway that is used to send encrypted traffic between an Azure Virtual Network and an on-premises location over the public internet. 
	* It provides a more secure connection from on-premises to Azure over the internet.
4.Azure Application Gateway:
	* Azure Application Gateway is a web traffic load balancer that enables you to manage traffic to your web applications. 
	* It is the connection through which users connect to your application. 
	* With Application Gateway you can route traffic based on source IP address and port to a destination IP address and port. 
	* You also can help protect a web application with a web application firewall, redirection, session affinity to keep a user on the same server, and many more configuration options.
5.Content Delivery Network:
	* A Content Delivery Network (CDN) is a distributed network of servers that can efficiently deliver web content to users. 
	* It is a way to get content to users in their local region to minimize latency. 
	* CDN can be hosted in Azure or any other location. 
	* You can cache content at strategically placed physical nodes across the world and provide better performance to end users. 
	* Typical usage scenarios include web applications containing multimedia content, a product launch event in a region, or any event where you expect a high bandwidth requirement in a region.
```
Walkthrough-Create a virtual network  

https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/03-Create%20a%20virtual%20network.md 


**Azure data categories**
```
* We can generally think of data as structured, semi-structured, and unstructured.

1.Structured data:
	* Structured data is data that adheres to a schema, so all the data has the same fields or properties.
	* Structured data can be stored in a database table with rows and columns.
	* Structured data relies on keys to indicate how one row in a table relates to data in another row of another table.
	* Structured data is also known as relational data. The data's schema defines the table of data, the fields in the table, and the clear relationship between the two.
	* Structured data is easy to enter, query, and analyze because all the data follows the same format.
	* Examples of structured data include sensor data or financial data.

2.Semi-structured data
	* Semi-structured data is less organized than structured data.
	* Semi-structured data is not stored in a relational format, meaning the fields do not neatly fit into tables, rows, and columns.
	* Semi-structured data contains tags that make the organization and hierarchy of the data apparent.
	* Semi-structured data is also known as non-relational or NoSQL data.
	* Examples of semi-structured data include books, blogs, and HTML documents.
	
3.Unstructured data
	* Unstructured data has no designated structure.
	* Unstructured data can hold any kind of data.
	* Unstructured data is becoming more prominent as businesses try to tap into new data sources.
	* Examples of unstructured data include a PDF document, a JPG image, a JSON file, and video content.
 
There are different Azure products to support each data type.

```
**Azure storage services**
```
* Azure Storage is a service that you can use to store files, messages, tables, and other types of information. 
* You can use Azure Storage on its own (for example as a file share), but developers also often use it as a store for working data. 
* Such stores can be used by websites, mobile apps, desktop applications, and many other types of custom solutions. 
* Azure Storage is also used by IaaS virtual machines, and PaaS cloud services.
* Some of the most common storage service types in Azure are disks, files, objects, queues, and tables.

1.Disk storage
	* Disk storage provides disks for virtual machines, applications, and other services to access and use as they need, similar to how they would in on-premises scenarios. 
	* Disk storage allows data to be persistently stored and accessed from an attached virtual hard disk. 
	* The disks can be managed or unmanaged by Azure, and therefore managed and configured by the user. 
	* Typical scenarios for using disk storage are if you want to lift and shift applications that read and write data to persistent disks, or if you are storing data that is not required to be accessed from outside the virtual machine to which the disk is attached.
	* Disks come in many different sizes and performance levels, from solid-state drives (SSDs) to traditional spinning hard disk drives (HDDs), with varying performance abilities.

2.Containers (Blobs)
	* Azure Blob storage is Microsoft's object storage solution for the cloud. 
	* Blob storage is optimized for storing massive amounts of unstructured data, such as text or binary data.
	* Blob storage is ideal for:
		Serving images or documents directly to a browser.
		Storing files for distributed access.
		Streaming video and audio.
		Storing data for backup and restore, disaster recovery, and archiving.
		Storing data for analysis by an on-premises or Azure-hosted service.
		
3.Files
	* Azure Files enables you to set up highly available network file shares that can be accessed by using the standard Server Message Block (SMB) protocol. 
	* That means that multiple VMs can share the same files with both read and write access. 
	* You can also read the files using the REST interface or the storage client libraries.
    * One thing that distinguishes Azure Files from files on a corporate file share is that you can access the files from anywhere in the world using a URL that points to the file and includes a shared access signature (SAS) token. You can generate SAS tokens; they allow specific access to a private asset for a specific amount of time.
	
	* File shares can be used for many common scenarios:
		1.Many on-premises applications use file shares. This feature makes it easier to migrate those applications that share data to Azure. If you mount the file share to the same drive letter that the on-premises application uses, the part of your application that accesses the file share should work with minimal, if any, changes.
        2.Configuration files can be stored on a file share and accessed from multiple VMs. Tools and utilities used by multiple developers in a group can be stored on a file share, ensuring that everybody can find them, and that they use the same version.
		3.Diagnostic logs, metrics, and crash dumps are just three examples of data that can be written to a file share and processed or analyzed later.

4.Queues
	* The Azure Queue service is used to store and retrieve messages. 
	* Queue messages can be up to 64 KB in size, and a queue can contain millions of messages. Queues are generally used to store lists of messages to be processed asynchronously.
	* For example, say you want your customers to be able to upload pictures, and you want to create thumbnails for each picture. You could have your customer wait for you to create the thumbnails while uploading the pictures. An alternative would be to use a queue. When the customer finishes their upload, write a message to the queue. Then have an Azure Function retrieve the message from the queue and create the thumbnails. Each of the parts of this processing can be scaled separately, giving you more control when tuning it for your usage.
	* For any scalable application architercture we need Queue.(ie Async mode). Otherwise it will be a tight coupling between source and destination.

5.Tables
	* Azure Table storage stores large amounts of structured data. 
	* The service is a NoSQL datastore which accepts authenticated calls from inside and outside the Azure cloud. 
	* Azure tables are ideal for storing structured, non-relational data. Common uses of Table storage include:
	* Storing TBs of structured data capable of serving web scale applications.
    * Storing datasets that don't require complex joins, foreign keys, or stored procedures and can be denormalized for fast access.
	* Quickly querying data using a clustered index.
    * You can use Table storage to store and query huge sets of structured, non-relational data, and your tables will scale as demand increases.	
```

Walkthrough-Create Blob storage 
 
https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/04-Create%20Blob%20storage.md 


**Azure database services**
```
* Azure database services are fully managed PaaS database services that free up valuable time you’d otherwise spend managing your database. 
* Enterprise-grade performance with built-in high availability means you can scale quickly and reach global distribution without worrying about costly downtime. 
* Developers can take advantage of industry-leading innovations such as built-in security with automatic monitoring and threat detection, automatic tuning for improved performance, and turnkey global distribution.
* Some of the most common data service types in Azure are:

1.Azure Cosmos DB:
	* Microsoft Azure Cosmos DB is a globally distributed database service that enables you to elastically and independently scale throughput and storage across any number of Azure's geographic regions. 
	* It supports schema-less data that lets you build highly responsive and Always On applications to support constantly changing data. 
	* You can use Cosmos DB to store data that is updated and maintained by users around the world. 
	* It makes it easy to build scalable, highly responsive applications at global scale.

2.Azure SQL Database:
    * Azure SQL Database is a relational database as a service (DaaS) based on the latest stable version of Microsoft SQL Server database engine. 
	* SQL Database is a high-performance, reliable, fully managed and secure database that you can use to build data-driven applications and websites in the programming language of your choice without needing to manage infrastructure.

Azure Database Migration:
The Azure Database Migration Service is a fully managed service designed to enable seamless migrations from multiple database sources to Azure data platforms with minimal downtime (online migrations). 
The service uses the Microsoft Data Migration Assistant to generate assessment reports that provide recommendations to help guide you through required changes prior to performing a migration. Once you assess and perform any remediation required, you're ready to begin the migration process. The Azure Database Migration Service performs all of the required steps.

Other database service offerings:
https://azure.microsoft.com/en-us/product-categories/databases/

```
Walkthrough-Create a SQL database  

https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/05-Create%20a%20SQL%20database.md


**Azure Marketplace**
```
Azure Marketplace allows customers—mostly IT professionals and cloud developers—to find, try, purchase, and provision applications and services from hundreds of leading service providers, all certified to run on Azure.
```

-------------------------
### Azure Solutions  
**IOT**
```
* People can access more information than ever before. 
* It began with personal digital assistants (PDAs), then morphed into smartphones.
* Now there are smart watches, smart thermostats, even smart refrigerators
* Now the internet allows any item that's online capable to access valuable information. 
* The Internet of Things (IoT) is the ability for devices to garner and then relay information for data analysis.
* There are many services that can assist and drive end-to-end solutions for IoT on Azure. 
* Two of the core Azure IoT service types are Azure IoT Central, and Azure IoT Hub.

1.IoT Central: 
	* Is a fully managed global IoT software as a service (SaaS) solution that makes it easy to connect, monitor, and manage your IoT assets at scale. 
	* No cloud expertise is required to use IoT Central. 
	* As a result, you can bring your connected products to market faster while staying focused on your customers.

2.Azure IoT Hub:
	* Azure IoT Hub is a managed service hosted in the cloud that acts as a central message hub for bi-directional communication between your IoT application and the devices it manages. 
	* You can use Azure IoT Hub to build IoT solutions with reliable and secure communications between millions of IoT devices and a cloud-hosted solution backend. 
	* You can connect virtually any device to your IoT Hub.
	* IoT Hub supports communications both from the device to the cloud and from the cloud to the device. 
	* It also supports multiple messaging patterns such as device-to-cloud telemetry, file upload from devices, and request-reply methods to control your devices from the cloud. 
	* IoT Hub monitoring helps you maintain the health of your solution by tracking events such as device creation, device failures, and device connections.
	* IoT Hub's capabilities help you build scalable, full-featured IoT solutions such as managing industrial equipment used in manufacturing, tracking valuable assets in healthcare, and monitoring office building usage.


IOT product selector(Helps you to determine what product is best for your situation): https://azure.microsoft.com/en-us/overview/iot/product-selector/


```
Walkthrough-Implementation of the azure IOT Hub

https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/06-Implement%20the%20Azure%20IoT%20Hub.md


**BigData and Analytics**
```
* Data comes in all types of forms and formats. 
* When we talk about Big Data, we're referring to large volumes of data. 
* Data from weather systems, communications systems, imaging platforms, and many other scenarios generate large amounts of data. 
* This amount of data becomes increasingly hard to make sense of and make decisions around. 
* The volumes are so large that traditional forms of processing and analysis are no longer appropriate.

* Open source cluster technologies have been developed, over time, to try to deal with these large data sets. 
* Microsoft Azure supports a broad range of technologies and services to provide big data and analytic solutions. 
* Some of the most common big data and analytic service types in Azure are Azure SQL Data Warehouse, HDInsight, and Data Lake Analytics

1.Azure SQL Data Warehouse:
	* Azure SQL Data Warehouse is a cloud-based Enterprise Data Warehouse (EDW) that leverages MPP(Massive parellel processing) to run complex queries quickly across petabytes of data. 
	* You can use SQL Data Warehouse as a key component of a big data solution by importing big data into SQL Data Warehouse with simple PolyBase Transact-SQL (T-SQL) queries, and then use the power of MPP to run high-performance analytics. 
	* Once data is stored in SQL Data Warehouse, you can run analytics at massive scale. 
	* Compared to traditional database systems, analysis queries finish in seconds instead of minutes, or hours instead of days
2.Azure HDInsight
	* Azure HDInsight is a fully managed, open-source analytics service for enterprises. 
	* It is a cloud service that makes it easier, faster, and more cost-effective to process massive amounts of data. 
	* HDInsight allows you run popular open-source frameworks and create cluster types such as Apache Spark, Apache Hadoop, Apache Kafka, Apache HBase, Apache Storm, Machine Learning Services. 
	* HDInsight also supports a broad range of scenarios such as extraction, transformation, and loading (ETL); data warehousing; machine learning; and IoT.
	* https://azure.microsoft.com/en-us/services/hdinsight/
3.Azure Data Lake Analytics
	* Azure Data Lake Analytics is an on-demand analytics job service that simplifies big data. 
	* Instead of deploying, configuring, and tuning hardware, you write queries to transform your data and extract valuable insights. 
	* The analytics service can handle jobs of any scale instantly by setting the dial for how much power you need.
	* You only pay for your job when it is running, making it more cost-effective.
	

A full list of big data and analytics services available with Azure:
https://azure.microsoft.com/en-us/product-categories/analytics/
```

**AI**
```
Artificial Intelligence, in the context of cloud computing, is based around a broad range of services, the core of which is Machine Learning. 
Machine Learning is a data science technique that allows computers to use existing data to forecast future behaviors, outcomes, and trends. 
Using machine learning, computers learn without being explicitly programmed.
Forecasts or predictions from machine learning can make apps and devices smarter. 
For example, when you shop online, machine learning helps recommend other products you might like based on what you've purchased. Or when your credit card is swiped, machine learning compares the transaction to a database of transactions and helps detect fraud. And when your robot cleaner vacuums a room, machine learning helps it decide whether the job is done.

Some of the most common Artificial Intelligence and Machine Learning service types in Azure are:

1.Azure Machine Learning Service:-
	* The Azure Machine Learning service(https://azure.microsoft.com/en-us/services/machine-learning/) provides a cloud-based environment you can use to develop, train, test, deploy, manage, and track machine learning models. 
	* It fully supports open-source technologies, so you can use tens of thousands of open-source Python packages with machine learning components such as TensorFlow and scikit-learn. Rich tools, such as Jupyter notebooks or the Visual Studio Code Tools for AI, make it easy to interactively explore data, transform it, and then develop, and test models. 
	* Azure Machine Learning service also includes features that automate model generation and tuning to help you create models with ease, efficiency, and accuracy.
	* The Azure Machine Learning service can auto-generate a model and auto-tune it for you. 
	* It will let you start training on your local machine, and then scale out to the cloud. When you have the right model, you can easily deploy it in a container such as Docker in Azure. Use Machine Learning service if you work in a Python environment, you want more control over your machine learning algorithms, or you want to use open-source machine learning libraries.
2.Azure Machine Learning Studio
	* Azure Machine Learning Studio is a collaborative, drag-and-drop visual workspace where you can build, test, and deploy machine learning solutions without needing to write code. 
	* It uses pre-built and pre-configured machine learning algorithms and data-handling modules. 
	* Use Machine Learning Studio when you want to experiment with machine learning models quickly and easily, and the built-in machine learning algorithms are enough for your solutions. 
	* It does not provide as much control over machine learning algorithms as the Machine Learning Service we discussed earlier.



Note: A full list of Artificial Intelligence and Machine Learning services is available. @ https://azure.microsoft.com/en-us/services/
```

**Serverless Computing**
```
https://azure.microsoft.com/en-us/solutions/serverless/
	* Serverless computing is a cloud-computing execution model in which the cloud provider runs the server, and dynamically manages the allocation of machine resources. 
	* Pricing is based on the actual amount of resources consumed by an application, rather than on pre-purchased units of capacity.
	* Serverless computing is a cloud-hosted execution environment that runs your code but abstracts the underlying hosting environment. You create an instance of the service and you add your code. 
	* No infrastructure configuration or maintenance is required, or even allowed.
	* You configure your serverless apps to respond to events. An event could be a REST endpoint, a periodic timer, or even a message received from another Azure service. 
	* The serverless app runs only when it's triggered by an event.
	* Scaling and performance are handled automatically, and you are billed only for the exact resources you use. You don't even need to reserve resources.

Some of the most common serverless service types in Azure are 
1.Azure Functions 
2.Azure Logic Apps
3.Azure Event Grid.
```
Walkthrough-Implement Azure functions  

https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/07-Implement%20Azure%20Functions.md


DevOps
```
https://azure.microsoft.com/en-us/solutions/devops/
	* DevOps (Deployment and Operations) brings together people, processes, and technology, automating software delivery to provide continuous value to your users. 
	* Some of the main DevOps services available with Azure are 
	
1.Azure DevOps Services
	* DevOps Services provides development collaboration tools including high-performance pipelines, free private Git repositories, configurable Kanban boards, and extensive automated and cloud-based load testing. DevOps Services was formerly known as Visual Studio Team Services (VSTS).
	* https://azure.microsoft.com/en-us/services/devops/
2.Azure DevTest Labs.
	* Lab Services is a service that helps developers and testers quickly create environments in Azure, while minimizing waste and controlling cost. 
	* Users can test their latest application versions by quickly provisioning Windows and Linux environments using reusable templates and artifacts. 
	* You can easily integrate your deployment pipeline with DevTest Labs to provision on-demand environments. 
	* With DevTest Labs you can scale up your load testing by provisioning multiple test agents and create pre-provisioned environments for training and demos. 
	* Lab Services was formally known as DevOps Test. 
```

Azure App Service
```
	* With Azure App Service you can quickly and easily build web and mobile apps for any platform or device. 
	* Azure App Service enables you to build and host web apps, mobile back ends, and RESTful APIs in the programming language of your choice without managing infrastructure.
	* It offers auto-scaling and high availability, supports both Windows and Linux, and enables automated deployments from GitHub, Azure DevOps, or any Git repo.

Key features of Azure App Service
1.Multiple languages and frameworks 
2.DevOps optimization
3.Global scale with high availability
4.Connections to SaaS platforms and on-premises data
5.Security and compliance
6.Application templates
7.Visual Studio integration
8.API and mobile features
9.Serverless code
```

Walkthrough-Create a Web App

https://github.com/MicrosoftLearning/AZ-900T0x-MicrosoftAzureFundamentals/blob/master/Instructions/Walkthroughs/08-Create%20a%20Web%20App.md


-------------------------
### Azure Management Tools

**Azure Management Tools**
```
* There are tools available for the command line, language-specific Software Development Kits (SDKs), developer tools, tools for migration, and many others

Azure Portal:
	* The Azure portal is a public website that you can access with any web browser. 
	* Once you sign-in with your Azure account, you can create, manage, and monitor any available Azure services
Azure PowerShell:
	* Azure PowerShell is a module that you add to Windows PowerShell or PowerShell Core that enables you to connect to your Azure subscription and manage resources. 
	* Azure PowerShell requires Windows PowerShell to function. 
	* PowerShell provides services such as the shell window and command parsing. 
	* Azure PowerShell then adds the Azure-specific commands
	* For example, Azure PowerShell provides the New-AzVM command that creates a virtual machine for you inside your Azure subscription. 
	* Note: PowerShell Core is a cross-platform version of PowerShell that runs on Windows Linux or macOS.
Azure Command Line Interface (CLI):
	* Azure CLI is a cross-platform command-line program that connects to Azure and executes administrative commands on Azure resources. 
	* *To create a VM, you would open a command prompt window, sign in to Azure using the command az login, create a resource group, then use a command  to create VM:
Azure Cloud Shell:
	* Azure Cloud Shell is a browser-based scripting environment in your portal. 
	* It provides the flexibility of choosing the shell experience that best suits the way you work. 
	* Linux users can opt for a Bash experience, while Windows users can opt for PowerShell.
	*A storage account is required to use the cloud shell and you will be prompted to create one when accessing the Azure cloud shell.
	* Note: You can access Azure Cloud Shell through the portal.
Azure Mobile App:
	* The Microsoft Azure mobile app allows you to access, manage, and monitor all your Azure accounts and resources from your iOS or Android phone or tablet.
Azure REST API:
	* Representational State Transfer (REST) APIs are service endpoints that support sets of HTTP operations (methods), which provide CRUD access to the service's resources. 
	* A REST API defines a set of functions which developers can perform requests and receive responses via HTTP protocol such as GET and POST.
```

**Azure Advisor**
```
* Azure Advisor is a free service built into Azure that provides recommendations on high availability, security, performance, and cost. 
* Advisor analyzes your deployed services and looks for ways to improve your environment across those four areas.

With Azure Advisor, you can:

1. Get proactive, actionable, and personalized best practices recommendations.
2. Improve the performance, security, and high availability of your resources as you identify opportunities to reduce your overall Azure costs.
3. Get recommendations with proposed actions inline.
```
Try-  
Create a VM with a Template  
Create a VM with PowerShell  
Create a VM with the CLI  

-------------------------
