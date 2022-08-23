## 2. Cloud Concepts
-----------------
Consumption-based pricing is indeed when you are charged for only what you use (pay-as-you-go rate). Consumption-based pricing is not limited to free accounts, and the services are not necessarily consumed all the time.

Infrastructure as a service (IaaS) is a type of cloud computing service that offers essential compute, storage, and networking resources on demand, on a pay-as-you-go basis. IaaS lets you bypass the cost and complexity of buying and managing physical servers and datacenter infrastructure. Each resource is offered as a separate service component, and you only pay for a particular resource for as long as you need it.

Fault tolerance means a failure can occur on Azure services and applications, but it will not affect its availability.

Serverless computing solutions provide a simple way to create manageable and scalable solutions at low costs. There is always a server somewhere to run your application, but you don't control it. Serverless is a kind of extreme PaaS.

Cloud agility is tied to the rapid provisioning of computer resources. Cloud environments can usually provide new compute instances or storage in minutes, a far cry from the common weeks (or months, in some organizations) that the same provisioning process can take in typical IT shops.

Elasticity is a core benefit of cloud computing and lets even small businesses take advantage of the cloud.
Elasticity: The ability to quickly expand or decrease computer processing, memory, and storage resources.

Microsoft defines private clouds as being able to be hosted at your datacenter or hosted by a third-party service. Microsoft considers private clouds as offering more flexibility, control, and scalability. Note: Other cloud vendors would not agree with those advantages of private clouds, but it is best to be aware of Microsoft's view in case it comes up on the exam.

Microsoft defines hybrid cloud as combining a public cloud (such as Azure) with on-premises infrastructure (private cloud).

A **private cloud** consists of cloud computing resources used exclusively by one business or organization. The private cloud can be physically located at your organization’s on-site datacenter, or it can be hosted by a third-party service provider. But in a private cloud, the services and infrastructure are always maintained on a private network, and the hardware and software are dedicated solely to your organization.

Private cloud - High Sclalability & Improved Security.

Scaling up/down is making a resource, such as a VM, larger or smaller. This is also known as scaling vertically. Scaling out is adding more resources of the same type, known as scaling horizontally.

Knowing the difference between OpEx and CapEx is critical to get the best value out of Azure for your company. Capital expenditures (CapEx) generally result in the acquisition and maintenance of assets, such as server hardware. Operating expenditures (OpEx) are the ongoing costs of running a business, such as paying for cloud services on a recurring basis. By moving costs to OpEx, businesses can plan for ongoing costs rather than large investments.

High availability is one of the core benefits of using cloud computing. It ensures backup resources are ready to take over any workload.

Scalability is a core benefit of cloud computing and allows any application to add resources almost instantly as demand increases. Azure Documentation: https://docs.microsoft.com/en-us/azure/architecture/framework/scalability/design-scale

A hybrid cloud model is the best of private and public cloud that can be used to avoid disruptions and outages, adhere to regulation and governance, span solutions across both public and private cloud, and alleviate CapEx investments.




## 3. Azure Architecture
---------------------

An **Azure Region** is a set of datacenters, deployed within a latency-defined perimeter and connected through a dedicated regional low-latency network. With more global regions than any other cloud service provider, Azure gives customers the flexibility to deploy applications where they need. An Azure region has discrete pricing and service availability.
https://azure.microsoft.com/en-au/global-infrastructure/

An **Availability** Set consists of two or more virtual machines in the same physical location within an Azure region. This configuration ensures that only a subset of the virtual machines in an availability set will be affected in the event of hardware failure or OS update, or a complete data center outage. This configuration offers 99.95% SLA.

**Azure Zones** are individual physical locations within a region. Each zone is made up of one or more datacenters equipped with independent power, cooling, and networking. SLA = 99.99%

When you deploy your resources using **ARM templates**, you can be confident it happens in the same way every single time. Your resources will be deployed in a consistent state.
https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/overview

**Azure Resource Manager** enables you to create, update, and delete resources in your Azure account.

**Azure Resource Manager** handles the request for any Azure tools, APIs, or SDKs.

When a **resource group** is removed or deleted, all of the resources within it are deleted with it. You can remove resource groups at any time. To delete a resource group, you need access to the delete action. You also need delete for all resources in the resource group. If you have the required access, but the delete request fails, it may be because there's a lock on the resources or resource group. Even if you didn't manually lock a resource group, it may have been automatically locked by a related service. Or, the deletion can fail if the resources are connected to resources in other resource groups that aren't being deleted. For example, you can't delete a virtual network with subnets that are still in use by a virtual machine.
https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/delete-resource-group?tabs=azure-cli#required-access-and-deletion-failures

Resources belong to a resource group, which can be a geographical, logical, customer-specific, or any other type of grouping.

**Azure Blueprints** is a *declarative way to orchestrate the deployment of various resource templates* and other artifacts such as: - *Role assignments* - *Policy assignments* - *Azure Resource Manager templates (ARM templates)* - *Resource groups*

## 4. Compute
---------

Infrastructure as a Service includes services that emulate hardware, such as virtual machines, networks, and storage.

A fully managed platform means the provider manages the infrastructure layer, such as VMs, disks, networks, and more. You only have to focus on the core functionality of your application. Fully managed services on Azure are available on all subscription types and come at no extra cost.

Azure VMs are close to a on premise windows machine. So, if asked easiest way to lift & sift a on-premise machine to Azure - Answer will be by creating a VM.

Azure virtual machine **scale sets** let you create and manage a group of load balanced VMs. The number of VM instances can automatically increase or decrease in response to demand or a defined schedule. Scale sets provide high availability to your applications and allow you to centrally manage, configure, and update a large number of VMs. With virtual machine scale sets, you can build large-scale services for areas such as compute, big data, and container workloads. 
https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/overview

Three type of App Services:
1.Web Apps allows you to easily deploy web-based applications with a number of languages.
2.Web App for Containers makes it simple to deploy web applications based in containers.
3.API Apps is specifically used for building apps that will host APIs (application programming interfaces) used by other applications.

Virtual machines on Azure abstract away the physical hardware layer, so you don't need to worry about maintaining physical hardware. Microsoft handles this instead.

**Azure Functions** are the smallest compute services on Azure that represent a single function of compute. Functions can be called or invoked via standard web address (URL).
Azure Functions is a serverless solution that allows you to write less code, maintain less infrastructure, and save on costs. Instead of worrying about deploying and maintaining servers, the cloud infrastructure provides all the up-to-date resources needed to keep your applications running.
https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview

Azure Virtual Desktop (formerly Windows Virtual Desktop) helps you quickly set up an environment, and even lets you reuse any existing Windows 10 licenses you have.


## 5. Networking
-------------

**Network peering** allows you to connect multiple virtual networks over the private Azure network for a private network connection.

A **load balancer** sits in front of two or more virtual machines to manage, and balance, the load to the virtual machines. This can be based on amount of incoming traffic or specific properties in the traffic. A load balancer has nothing to do with virtual disks, and the *max number of VMs to manage goes up to 1,000.* A load balancer ensures only healthy instances receive traffic and will stop sending traffic to any server that does not pass health checks. All Azure load balancers can log traffic that passes through them.

You can use *multi-site hosting* to use the same **Application Gateway** for more than one website. You can, in fact, add up to 100 websites to the same instance of an Application Gateway. This will both save you on cost and complexity.

An **Application Gateway** is similar to a load balancer, but it can *redirect traffic* based on attributes in the HTTP request, the request coming in from the internet. You can have a VM handling video, one handling images and so on. Application Gateways do not handle traffic security, nor manage any virtual networks.

**Azure Virtual Network** enables *Azure resources to securely communicate with each other*, the internet, and on-premises networks. Key scenarios that you can accomplish a virtual network include: *communication of Azure resources with the internet, communication between Azure resources, communication with on-premises resources, filtering network traffic, routing network traffic, and integration*

A **VPN gateway** is an important part of a hybrid Azure infrastructure. It allows *encrypted traffic* to flow between *on-premises services and Azure services*.

A **CDN** keeps a recent copy of your web application and can deliver this much faster to users close to an endpoint. CDNs can handle a lot more data than a typical web server, which makes it ideal to handle traffic spikes as well. CDNs don't generally handle individual traffic routing rules, nor security.

**ExpressRoute** lets you extend your on-premises networks into the Microsoft cloud over *a private connection with the help of a connectivity provider*. With ExpressRoute, you can establish connections to Microsoft cloud services, such as Microsoft Azure and Microsoft 365.

## 6. Storage
---------

**Azure Files** can be used to completely replace or supplement traditional on-premises file servers or NAS devices. Popular operating systems such as Windows, macOS, and Linux can directly mount Azure file shares wherever they are in the world. SMB Azure file shares can also be replicated with Azure File Sync to Windows Servers, either on-premises or in the cloud, for performance and distributed caching of the data where it's being used.
https://docs.microsoft.com/en-us/azure/storage/files/storage-files-introduction#why-azure-files-is-useful

**Azure Blob storage** is Microsoft's object storage solution for the cloud. Blob storage is optimized for storing massive amounts of unstructured data, such as text or binary data. Blob storage is ideal for storing data for backup and restore, disaster recovery, and archiving. Azure Documentation
https://docs.microsoft.com/en-us/azure/storage/common/storage-introduction#blob-storage

**Disk storage** is a full Virtual hard disk that you can access. It is ideal as the disk for a Virtual machine. In fact, when you create a Virtual machine, disk storage is created too.

A **storage account** provides *a unique namespace in Azure for your data*. Every object you store in Azure Storage has an address that includes your unique account name. The combination of the account name and the Azure Storage service endpoint forms the endpoints for your storage account. Your storage account name must be unique within Azure. No two storage accounts can have the same name. Reference: https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview#storage-account-endpoints

Azure offers four types of manage disk storage: Standard HDD, Standard SSD, Premium SSD, and Ultra Disk.

**Block blobs** are used for handling large amounts of data very effectively.
Append blobs are used for operations where you are *appending* new data to existing content, rather than replacing it. Picture this like a log that you're constantly adding to.

**Page blobs** are used for *random read/write* operations. Picture this like the computing equivalent of having a scrap piece of paper (or "page") on your desk to scribble notes on that you only need for temporary periods of time.

**Blob containers** on Azure act similar to directories in a file system. They can contain an unlimited number of blobs.


## 7. Database
-----------

Using Azure Database Migration Service, you can migrate directly from Microsoft SQL Server to Azure SQL. It is recommended by Azure to move your on-premises SQL Server instances to Azure SQL to improve efficiency and lower costs.

Azure SQL is a managed service, which means Microsoft takes care of all the hardware and maintenance tasks for running the database. You only have to worry about using the database for storing and retrieving data. There is no noticeable performance advantage with using either SQL service.

PostgreSQL is a valid source database when migrating to Azure DB for PostgreSQL using the Azure Database Service.
RDS PostgreSQL is a valid source database when migrating to Azure DB for PostgreSQL using the Azure Database Service.
https://docs.microsoft.com/en-au/azure/dms/resource-scenario-status#online-continuous-sync-migration-support

Cosmos DB is a globally scaled distributed database solution that offers very low latency, a range of tools to interact with the data, and near-infinite scaling to handle demand. Cosmos DB is not meant as a cheap storage service, nor for backup of data. Azure has archive data services for that.

The power of a database is how the data is sorted and indexed, as well as the flexibility in how to get the data out again. Databases are not cheaper, more secure, or more space efficient than other types of storage.



## 8. Authentication & Authorization
----------------------------------

Authentication is the process of determining that you are you. This is most commonly done using a username and password, but it could also be with a fingerprint or face recognition.

Authorization determines your access to a system once you have been authenticated. This could be the right to access a certain part, create a new customer, or install new software.

Azure multi-factor authentication (MFA) helps safeguard access to data and applications while maintaining simplicity for users. It provides additional security by requiring a second form of authentication and delivers strong authentication via a range of easy-to-use authentication methods, which are something you know, have, or are.

Single sign-on lets users use a single username and password to access all apps registered with Azure AD.

A single user can belong to a maximum of **500 Azure AD** tenants as a member or a guest.
https://docs.microsoft.com/en-us/azure/active-directory/enterprise-users/directory-service-limits-restrictions



## 9. Azure Solutions
-------------------

**Azure Synapse Analytics (formerly known as Azure SQL Data Warehouse)** is a PaaS offering that can run queries against *petabytes of data*, often used for reports and data analytics.

A model is the way you define what you want your machine learning implementation to learn. You give it a model, which is a set of rules, and the application then starts playing this model over and over again with the data you have provided. Over time, usually very fast, the model will find patterns in the data that follow the rules you have provided.

There are currently five services in Azure DevOps: Boards for managing and tracking projects; **Azure Pipelines** for building, testing, and deploying projects; **Azure Repos** for storing and managing code; **Azure Test Plans** for conducting manual tests and automating tests; and **Azure Artifacts** for hosting and sharing packages to share functionality across teams.

There are many Azure services for Internet of Things. Two of them are IoT Hub and IoT Central.

**IoT Central** - less development effort.

**IoT Hub** - More control & more development effort.

There are a lot of ways to *schedule, automate, and orchestrate* tasks and processes using **Logic Apps**.
Logic Apps connect systems both *inside and outside* of the Azure platform, integrating not only apps but also data flows, services, and entire systems.

Analyzing Big Data can often lead to more precise decision-making for a business, a cost reduction on the storage of the data using a service like Azure Data Lake, and better products that take customer feedback and behavior into account.

**Azure Data Lake Analytics** can run massively parallel data *transformation and processing* programs across petabytes of data. 

**Azure HDInsight** is an *open-source* analytics service for enterprises that makes it easy, fast, and *cost-effective* to process massive amounts of data.

## 10. Security
------------

**Azure Security Center** constantly reviews your active recommendations and calculates your secure score based on them.

**Azure Firewall** blocks any incoming or outgoing traffic that isn't specifically allowed *on a network*. 

A **Network Security Group** manages the traffic to *specific services*. 

**Azure DDoS Protection Service** protects against attacks.

a **load balancer** distributes traffic to specific VMs. 

**Microsoft Defender for Identity** helps you detect and investigate security incidents across your Azure accounts, both on-premises and in the cloud. It monitors users, devices, and resources in terms of their behavior. If any behavior is out of the ordinary, an alarm can be raised.

A distributed denial-of-service (DDoS) attack comes from a large number of sources with the sole aim of stopping your service. This is done through sending web traffic to your service until it can't handle it all and stops working. Azure has tools to protect against DDoS attacks, which sometimes aren't attacks at all but just increased visitor interest in services or content.

The **defense-in-depth** concept stipulates that you need more than just one security measure for your data and resources, such as firewalls, network gateways, and physical measures.

**Azure Information Protection** helps secure email, documents, and sensitive data inside and outside your company walls. You can *classify* sensitive data, *track activities* on shared files and documents, *collaborate securely*, and much more. There is no active security service included, such as scanning the files being protected.

Azure dedicated hosts run on their own dedicated hardware inside the Azure datacenter and only your chosen VMs will run on it.

**Azure Sentinel** will collate, aggregate, and analyze data from multiple Azure services to detect any unusual behavior or patterns. You can then take action on the information.

**Azure Key Vault** is a secure place to store passwords and other secrets. Once stored, you can never retrieve the actual value or keys, but you can share access to the value or specific versions of a secret with other third-party clients and other Azure services. You can also restrict or deny access easily and quickly, should it be necessary.

**Azure Policy** is used to enforce different rules and effects over your resources, such as limiting what actions different administrators can perform within resource group.

Appropriately configured **Network Security groups** allow you to *control all inbound and outbound traffic for your virtual machines.*

## 11. Privacy, Compliance & Trust
-------------------------------

**Locks** can be put on resources to make sure there aren't any accidental or nefarious actions taken on them. The two types of locks are **delete**, which means you can't delete the resource, and **read-only**, which means you can't make any changes to the resources.

Privacy is a core component of each and every Azure service, so there isn't a single service. All products are built with privacy as a first-class citizen.

You can use the **Trust Center** to find documentation on all the various compliance standards Azure adheres to. You can use the Service Trust Portal to read the audit reports for any part of Microsoft's products, including Azure.

**Azure Monitor** can accept data from almost any service *(Both Azure & on premise)*, in order to monitor their operation and health. You get a single dashboard to view all of the current metrics, or you can delve into the archived data through the interactive query language.

**Azure Service Health** notifies you about Azure service incidents and planned maintenance. You can use this information to take appropriate actions to limit any downtime. Azure Service Health can't receive data from any of your applications or third-party services. It is only for Azure.

Services in the China region are hosted on a physically isolated instance of Azure. It is operated by 21Vianet, a company based in China. All of your customer data is kept within China and is bound by Chinese regulations.

A security policy defines the desired configuration of your workloads and helps ensure you're complying with the security requirements of your company or regulators.

Role-based access control (RBAC) helps you manage who has access to Azure resources, what they can do with those resources, and what areas they have access to. You have very detailed control of resource actions, and you assign roles to users to let them take those actions. You can define as many roles as you wish in RBAC.

**Azure Activity Log** - it is a logging service that provides insight into subscription-level events that have occurred in Azure. This includes a range of data, from Azure Resource Manager operational data to updates on Service Health events. Events such as starting and stopping of virtual machines can be found here.

**NIST** - The National Institute of Standards and Technology (NIST) promotes and maintains measurement standards and guidance to help organizations assess risk. It defines the standards that are used by the United States government as well as the **US** Department of Defense (DoD).

The General Data Protection Regulation (EU) 2016/679 **("GDPR")** is a regulation in **EU** law on data protection and privacy for all individuals within the European Union (EU) and the European Economic Area (EEA). It also addresses the export of personal data outside the EU and EEA areas. The GDPR aims primarily to give control to individuals over their personal data and to simplify the regulatory environment for international business by unifying the regulation within the EU.

 **ISO** - The International Organization for Standardization (ISO) is an independent nongovernmental organization and the world's largest developer of voluntary international standards. 


## 12. Pricing
-------

The **pricing calculator** for Azure is a comprehensive tool you can use to estimate any combination of services on Azure. The Total Cost of Ownership Calculator can indicate the savings achieved by moving your on-premises services to Azure. The Azure portal can only estimate costs of existing services that you have in your account.

**Azure spending limits** are the recommended way to manage the total spend on your Azure subscription. When your usage results in charges that exhaust your spending limit, the services you deployed are disabled for the rest of that billing period.

A subscription represents a grouping of Azure resources. An invoice is generated at the subscription scope.

If you want to **raise the limit or quota above the default limit**, open an online customer support request at no charge. 

**Azure Cost Management** is a part of the Azure portal that can visualize your current and future costs. It also includes tools for financial governance to make sure you don't get unexpected costs from incorrect use of Azure resources.

The factors that influence the **price** of a service on Azure are *resource size, resource location, and the bandwidth* being used. How much you use a resource or the age of it do not influence the price.

The only way to **combine Azure subscriptions** is to open a support case with Microsoft. 


## 13. Support
-------

Service-level agreements are implicit for all Azure paid services. You get an SLA included with every subscription level and support level. In general, there are no SLAs associated with free products on Azure.

The Azure Q&A articles provide answers to a range of the most commonly asked questions. In particular, the focus is on foundational answers or answers to popular questions that are seen again and again.

The Azure documentation, technical forums, and official Azure social media accounts are all good ways to interact with experts and Azure professionals.

A support ticket is submitted through the Support section of the Azure portal. Depending on your support level, you will have various options to submit billing, technical, and other kinds of support tickets.

You may think this question is needlessly specific, but Microsoft loves to test students on the support matrix and you will likely get a question like this on the exam. Memorize the entire support matrix. No arguing. Do it now.
https://azure.microsoft.com/en-in/support/plans/


