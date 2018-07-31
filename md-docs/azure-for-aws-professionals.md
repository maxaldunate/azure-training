# Azure for AWS Professionals
[MsDocs](https://docs.microsoft.com/en-us/azure/architecture/aws-professional/)

* [AWS to Azure services comparison](https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services)

## Subscriptions

Unlike AWS, where any resources created under the AWS account are tied to that account, ***subscriptions exist independently of their owner accounts***, and can be reassigned to new owners as needed.

- Types of administrator accounts:
  * Account Administrator: subscription owner & billed
  * Service Adminsitrator: only one service administrator per subscription
  * Co-administrator: multiple co-administrator 

## Resource groups

Aws tagged vs always associated with one resource group.

## Management interfaces

* **Web** Aws Console vs Azure Portal
* **RestAPI** Programatic access (Both)
* **CLI** Both
* **PowerShell** Modules (even linux & Mac)
* **Templates** similar CloudFormation.  
  Cfn stacks azure resource group

***Third party management tools***  
- [Terraform - Hashicorp's](https://www.terraform.io/docs/providers/azurerm/)
- [NBetflix Spinnaker](https://www.spinnaker.io/)

## Regions and zones (high availability)

### Availability sets
* Level Rack failure.  
* To protect against localized hardware failures, such as a disk or network switch failing, deploy two or more VMs in an availability set
* Planned update and patching events affect only a subset of these VMs at any given time
* Latency very low

### Availability zones
* Level datacenter-wide failures
* Idem Aws AZ
* Latency low

### Paired regions
* Every regional has a pair (at least 300 miles far)
* Except Brazil South, same geo, tax & law
* Azure Traffic Manager to distribute traffic to different regions
* Latency mid to high

## Services

> [AWS to Azure services comparison](https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services)

### Compute
* Unlike AWS' per second billing, Azure on-demand VMs are billed by the minute.
* Azure has no equivalent to EC2 Spot Instances or Dedicated Hosts
* EBS similar Azure Storage for VM disks. Az premium sotrage eq Provisioned IOPS
* Aws Lambda 
  - Azure Functions
  - WebJobs. Scheduled or continuously running background tasks
  - Logic Apps. provides communications, integration, and business rule management services
* Aws Autoscaling
  - VM scale sets. identical set of VMs
  - App Service Autoscale. autoscale Azure App Service solutions
* Azure Batch
* Service Fabric  
  platform for developing and hosting scalable microservice solutions

### Storage
* Blob storage: same purpose as both AWS S3 and EBS
* Table storage: similar to AWS' SimpleDB and DynamoDB services
* Queue storage: messaging for workflow & communication between components of cloud services
* File storage: legacy applications using the standard server message block (SMB) protocol (Aws EFS)
* Azure Archive Blob Storage: comparable to AWS Glacier.
* Azure Cool Blob Storage tier: comparable to AWS S3 - Infrequent Access

### Networking
* ELB
  - Load Balancer: similar Classic LB (network level with failover capability)
  - Application Gateway: App LB
* Route 53
  - Azure DNS
  - Traffic Manager: provides DNS level traffic routing, load balancing, and failover capabilities.
* Aws Direct Connect
  - ExpressRoute: allows you to connect your local network directly to Azure resources using a dedicated private network connection

### Databases
* RDS
  - SQL database
  - Azure DB for MySQL
  - Azure DB for PostgreSQL
  - Other (SQL Server, Oracle, MySql) deployed using Azure VMs
  - Costs
    * Aws depends on CPU, RAM, storage and network bandwidth
	* Azure depends on storage, concurrent connections and throughput levels

### Security and identity
* Aws Directory Service (Aws Active Directory)
  - Azure AD: cloud based directory and identity management service
  - Azure AD B2B: enables access to your corporate applications from partner-managed identities
  - Azure AD B2C: service offering support for single sign-on and user management for consumer facing applications
  - Azure AD Domain Services: hosted domain controller service
* Added to Web application firewall (WAF), from third-party vendors like Barracuda Networks

### Application and messaging services
* SES: in Azure third-party solutions like Sendgrid provide email services
* SQS
  - Queue storage: within the Azure platform
  - Service Bus: also connect to remotely hosted applications and services
* Aws Device Farm: Azure Xamarin Test Cloud

### Analytics and Big Data
* In Azure: The Cortana Intelligence Suite  
  HDInsight, Data Factory, SQL Data Warehouse, Data Lake Storage, Machine Learning, Stream Analytics, Data Lake Analytics, PowerBI

### Internet of Things
* Azure IoT Hub
* Event Hubs

### Mobile Services
* Notifications: third-party services are needed for those delivery types

### Management and monitoring
* [Monitoring and diagnostics](https://docs.microsoft.com/en-us/azure/architecture/best-practices/monitoring)

The End