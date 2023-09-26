# What Is Cloud Computing?
In simple words cloud computing is the practice of using a network of remote servers hosted on the internet to store, manage, and process data, rather than a local server or a personal computer.

---
 
## What Is Amazon and AWS?
Amazon is a well-known and widely used online marketplace where you can buy a wide range of products, from books and electronics to household items and clothing. It started as an online bookstore and expanded into one of the largest e-commerce platforms globally.

AWS (Amazon Web Services) is a separate division of Amazon that provides a comprehensive set of cloud computing services. Think of it as a collection of powerful and flexible tools and resources that businesses and individuals can use to build and run their own applications and services on the internet. AWS offers a broad range of services, including computing power, storage, databases, networking, analytics, and much more. These services are accessible through the internet and allow users to pay for what they use on a pay-as-you-go basis. AWS has gained popularity due to its reliability, scalability, and extensive feature set, enabling organizations to innovate and scale their businesses without having to invest in and manage their own physical infrastructure.

---

## What Is Cloud Service Provider (CSP)?
In simple words, a Cloud Service Provider (CSP) is a company or organization that offers cloud computing services to individuals, businesses, and other entities. CSPs own and manage the underlying infrastructure, such as servers, storage systems, networking equipment, and software, required to deliver cloud services over the internet. CSPs offer a wide range of services, including virtual servers, storage, databases, networking, analytics, AI/ML capabilities, and more. These services can be accessed and utilized by customers on-demand, allowing them to scale their resources up or down as needed, pay only for what they use, and focus on their core business rather than worrying about infrastructure management.

Examples of well-known CSPs include Amazon Web Services (AWS), Microsoft Azure, Google Cloud Platform (GCP), IBM Cloud, and Oracle Cloud. Each CSP offers its own set of services and features, allowing customers to choose the provider that best meets their specific requirements.

---

## Most Common Cloud Services?
A cloud Service Provider (CPS) can have hundreds of cloud services that are grouped into various types of services. The 4 most common types of cloud services (also called the 4 core) for Infrastructure as a Service (IaaS) would be :
- **Compute** : Imagine having a virtual computer that can run application, programs and code. (ex. EC2 Virtual Machines in aws)
- **Networking** : Imagine having a virtual network defining internet connections or network isolations between services or outbound to the internet. (ex. VPC Private Cloud Network in aws)
- **Storage** : Imagine having a virtual hard-drive that can store files. (ex. EBS Virtual Hard-drives in aws)
- **Databases** : Imagine a virtual database for storing reporting data or a database for general purpose web-application. (ex. RDS SQL Databases in aws)

---

### Adavantages To Cloud
1. Cost-Efficiency:
    - Pay-as-You-Go: Cloud services typically follow a pay-as-you-go or subscription-based pricing model. This eliminates the need for upfront capital expenditures on hardware and software, allowing businesses to pay only for the resources they actually use.
    - Economies of Scale: Sharing the cost with other customers to get unbeatable savings. (Hunderds of thousands of customers utilizing a fraction of as server)

2. Scalability:
    - On-Demand Scaling: Cloud resources can be easily scaled up or down to meet changing workloads and demands. This flexibility allows businesses to adapt to seasonal variations or sudden spikes in traffic without over-provisioning.

3. Flexibility and Agility:
    - Rapid Deployment: Cloud services can be provisioned quickly, reducing the time it takes to set up new infrastructure or launch new applications.
    - Global Reach: Cloud providers often have data centers in multiple regions and countries, enabling businesses to expand their reach globally without the need for physical infrastructure in each location.

4. Reliability and Redundancy:
    - High Availability: Cloud providers typically offer high levels of uptime and availability through redundancy and failover mechanisms.
    - Data Backup and Recovery: Cloud services often include built-in data backup and disaster recovery capabilities, helping to protect against data loss.

5. Security:
    - Compliance and Certifications: Many cloud providers invest heavily in security measures, including data encryption, access controls, and compliance certifications (e.g., ISO 27001, SOC 2) to meet industry and regulatory standards.
    - Security Expertise: Cloud providers employ dedicated security teams with expertise in safeguarding data and infrastructure.

---

### What Is AWS Global Infrastructure?
Amazon Web Services (AWS) Global Infrastructure refers to the extensive and distributed network of data centers and cloud resources that AWS operates around the world to provide its cloud computing services. AWS has strategically positioned data centers in multiple geographic regions and availability zones to ensure high availability, fault tolerance, and low-latency access to its services for customers.

In simple words aws global infrastructure is globally distributed hardware and datacenters that are physically netwroked together to act as one large resource for the end customer.

The most important element of aws global infrastructure are regions and availability zones.
### What Are Regions (In AWS Global Infrastructure)?
Amazon Web Services (AWS) Regions are distinct geographical areas where AWS has established multiple data centers or data center clusters. Each AWS Region is designed to be isolated and independent of other regions, and it provides a set of AWS services to customers within that region. AWS currently operates a global network of Regions to support its cloud computing services.

Key points about AWS Regions include:
    
    - Geographical Isolation: Each AWS Region is physically isolated from other regions to provide fault tolerance and minimize the risk of service disruption due to natural disasters, power outages, or other regional issues.

    - Redundancy: Within each Region, AWS typically deploys multiple data centers known as Availability Zones (AZs). These AZs are designed to operate independently and provide redundancy and high availability for AWS services.

    - Service Availability: Not all AWS services are available in every Region. AWS determines which services are offered in a specific Region based on factors such as customer demand and the technical feasibility of deploying a service in that location.

    - Data Residency: Customers can choose to store their data and run their workloads in a specific Region to comply with data residency and compliance requirements. AWS provides tools and services to help customers manage data replication and backup across Regions.

    - Low-Latency Access: Customers can deploy their applications and services in a Region geographically closer to their end-users to reduce latency and improve performance.

    - Global Network Backbone: AWS operates a global network backbone that interconnects all Regions and AZs, ensuring reliable and low-latency communication between services and resources.

Each AWS Region is identified by a unique code (e.g., us-east-1 for US East (N. Virginia)) and is used by customers to specify the geographical location where they want to deploy their resources and data.

### When you choose a region there are four factors you need to consider:
1. What Regulatory Compliance does this region meet?
2. What is the const of AWS services in this region?
3. What AWS services are available in this region?
4. What is the distance or latency to my end-users?


### What Are Availability Zones?
An Availability Zone (AZ) is a concept used in cloud computing infrastructure, it represents a physically isolated and independent data center or data center cluster within a specific geographic region. The primary purpose of Availability Zones is to enhance the availability, fault tolerance, and resilience of cloud services and applications.

Note : A datacenter is a secured builiding that contains hundreds of thousands of computers.

A region will *generally contains 3 Availabilit Zones(AZ). Datacenters within a region will be isolate from each other(different buildings). But they will be close enough to provide low-latency(less than 10ms). Its common practice to run workloads in at least 3 AZs to ensure services remain available in case one or two datacenters fail (High Availability). AZs are represented by a Region Code, followed by a letter identifier eg. `us-east-1a`

![](./imgs/region_AZ.png)


### AWS Global Network
The AWS Global Network represent the **interconnection between AWS Global Infrastructure.** Commonly referred to as the `The Backbone of AWS`.

---

### What Is Point of Presence (PoP) in AWS?
In the context of Amazon Web Services (AWS) and cloud computing, a "Point of Presence" (PoP) usually refers to a physical location where network infrastructure, such as servers and routers, is deployed to provide network connectivity and services. These PoPs are strategically placed in various cities and regions around the world to enhance the performance, reliability, and availability of network services. However, it's important to note that AWS doesn't commonly use the term "Point of Presence" in the same way that traditional network providers or Content Delivery Networks (CDNs) might use it.

Here's how PoPs are typically used in the context of AWS and cloud computing:

1. Edge Locations: The term "Point of Presence" in AWS is often associated with "Edge Locations." AWS Edge Locations are part of Amazon CloudFront, AWS's content delivery network (CDN). These Edge Locations are distributed globally and serve as caching and content delivery points. They are strategically placed in metropolitan areas to provide low-latency access to cached content for end-users. When an end-user requests content, CloudFront serves it from the nearest Edge Location, reducing latency and improving performance.

2. Direct Connect Locations: AWS also has "Direct Connect Locations" that are spread across various cities worldwide. These locations are used for AWS Direct Connect, a service that provides dedicated network connections between on-premises data centers and AWS. Customers can establish private and high-speed connections to AWS resources via Direct Connect, improving network performance and reliability.

3. Regional Data Centers: AWS Regions comprise multiple data centers or data center clusters located in different geographic regions around the world. Each Region can be considered a point of presence for AWS services. Within each Region, there are Availability Zones (AZs), which are isolated and redundant data center facilities. These AZs provide high availability and fault tolerance for AWS services and customer workloads.

![](./imgs/pop.png)

---

### What Is Amazon CloudFront service?
Amazon CloudFront is a content delivery network (CDN) service provided by Amazon Web Services (AWS). It is designed to accelerate the delivery of static and dynamic web content, including web pages, images, videos, application data, and APIs, to end-users around the world. CloudFront leverages a global network of edge locations to reduce latency, improve website and application performance, and lower the load on origin servers.

Key features and characteristics of Amazon CloudFront include:

- Global Network of Edge Locations: CloudFront has a vast network of edge locations strategically distributed across the globe. As of my last knowledge update in September 2021, AWS had over 250 edge locations in more than 90 cities worldwide. These edge locations are used to cache and serve content to end-users.

- Low Latency: CloudFront serves content from the edge location that is geographically closest to the end-user, reducing the time it takes for content to reach the user's device. This low-latency access improves the user experience for websites and applications.

- Content Caching: CloudFront caches copies of content at its edge locations. When an end-user requests content, CloudFront checks if it's already in the cache. If so, it serves the content directly from the cache, reducing the load on the origin server and accelerating delivery.

- Support for Dynamic Content: While CloudFront is often associated with caching static content, it can also accelerate the delivery of dynamic content and APIs by using various caching and compression techniques.

- SSL/TLS Encryption: CloudFront supports secure communication via SSL/TLS encryption. You can use CloudFront to deliver content securely over HTTPS.

- Customization: CloudFront provides fine-grained control over cache behaviors and content delivery. You can configure cache expiration, set cache headers, and define caching rules based on URLs or query parameters.

- Origin Fetch: If content is not available in the edge location cache or has expired, CloudFront fetches it from the origin server, which can be an Amazon S3 bucket, an EC2 instance, or other HTTP servers. You can also configure CloudFront to use AWS Lambda functions for serverless content generation.

- Content Compression: CloudFront can compress content on the fly, reducing the size of files before they are sent to the end-user's device. This reduces bandwidth costs and improves load times.

- Streaming Services: CloudFront supports streaming media delivery, enabling you to stream audio and video content to global audiences with low latency and high reliability.

- Distributed Denial of Service (DDoS) Protection: CloudFront includes DDoS protection to help protect your applications and content from malicious traffic and attacks.

- Origin Shield: AWS offers an optional Origin Shield feature that can help protect your origin server from traffic spikes and reduce the load on the origin.

- Real-Time Analytics: CloudFront provides real-time monitoring and analytics through AWS CloudWatch and Amazon CloudFront reports, allowing you to track the performance of your content and troubleshoot issues.


### Amazon S3 Transfer Acceleration
Amazon S3 Transfer Acceleration is a feature offered by Amazon Web Services (AWS) that allows you to accelerate the transfer of data to and from Amazon Simple Storage Service (S3) buckets. It is designed to enhance the speed and efficiency of data uploads and downloads to and from S3 by leveraging Amazon CloudFront's content delivery network (CDN) infrastructure.

S3 Transfer Acceleration uses Amazon CloudFront's globally distributed edge locations to accelerate data transfers. When you enable Transfer Acceleration on an S3 bucket, it automatically routes data through the nearest CloudFront edge location, reducing the distance and network hops data must travel. This results in faster uploads and downloads. To enable Transfer Acceleration on an S3 bucket, you don't need to make changes to your application code or network configuration. You simply enable Transfer Acceleration for the bucket, and S3 takes care of the rest. When you enable Transfer Acceleration, S3 provides a unique endpoint for accelerated transfers. Instead of using the standard S3 endpoint (e.g., s3.amazonaws.com), you use a specialized endpoint (e.g., bucketname.s3-accelerate.amazonaws.com) to take advantage of acceleration.

### AWS Global Accelerator
AWS Global Accelerator is a service offered by Amazon Web Services (AWS) that helps improve the availability and performance of applications by providing static IP addresses and automatic routing to optimal AWS endpoints. It is designed to distribute incoming network traffic across multiple AWS regions and AWS and non-AWS resources, improving fault tolerance and ensuring that end-users are directed to the best-performing endpoint based on health, geography, and routing policies.

![](./imgs/pop_services.png)

---

### AWS Direct Connect
Amazon Direct Connect is a network service provided by Amazon Web Services (AWS) that allows you to establish dedicated and private network connections (called `connections`) between your on-premises data centers or corporate network and AWS resources. It is designed to provide secure, high-bandwidth, and low-latency connections, bypassing the public internet, and enabling direct access to AWS services and resources.

Direct Connect provides a private network connection to AWS, ensuring that your data does not traverse the public internet. This improves security, reliability, and performance for data transfer and application workloads. You can provision Direct Connect connections with high bandwidth capacities, ranging from 1 Gbps to 100 Gbps, depending on your requirements. This enables the transfer of large volumes of data to and from AWS.

![](./imgs/direct_connect.png

---

### AWS Wavelength Zones
AWS Wavelength Zones are specialized infrastructure deployments provided by Amazon Web Services (AWS) in collaboration with telecommunications partners. These zones are designed to bring AWS services closer to the edge of the 5G wireless network, enabling ultra-low-latency and high-throughput connectivity for applications that require real-time data processing and communication.)

---

### Data Residency, Compliance Boundaries, Data Sovereignty
1. Data Residency : The physical or geographic location of where an organization or cloud resources reside.
2. Compliance Boundaries : A regulatory compliance (legal requirement) by a government or organization that describes where data and cloud resources are allowed to reside.
3. Data Sovereignty : Data Sovereignty is the jurisdictional control or legal authority that can be asserted over data because it's physical location is within jurisdictional boundaries.

---

### AWS Ground Station Service
AWS Ground Station is a fully managed service provided by Amazon Web Services (AWS) that enables customers to control and communicate with satellites, process satellite data, and downlink information from satellites to the AWS cloud infrastructure. It simplifies and accelerates the process of using satellite data for a wide range of applications, including Earth observation, communications, weather monitoring, and more.

AWS Ground Station provides access to a network of ground stations around the world. Customers can use these ground stations to communicate with their satellites in orbit.

---

### Elastic Load Balancer
ELB stands for Elastic Load Balancing, and it is a service provided by AWS (Amazon Web Services) that helps distribute incoming network traffic across multiple Amazon EC2 instances or other resources to ensure high availability, fault tolerance, and scalability for your applications.

Here are the key features and benefits of the ELB service in AWS:

1. Load Balancing: ELB automatically distributes incoming traffic to multiple instances or resources within a specific AWS Region. This helps distribute the workload evenly, preventing any single instance from being overwhelmed.

2. High Availability: ELB itself is designed for high availability. It operates across multiple Availability Zones (AZs) within a Region, so if one AZ experiences issues, traffic is automatically routed to healthy instances in other AZs.

3. Fault Tolerance: ELB continually monitors the health of the instances or resources it routes traffic to. If an instance becomes unhealthy or fails, ELB stops sending traffic to that instance and redirects it to healthy instances.

4. SSL/TLS Termination: ELB can handle SSL/TLS encryption and decryption, offloading the SSL/TLS processing from the instances. This simplifies the management of SSL/TLS certificates and improves the performance of your applications.

5. Session Stickiness: ELB can be configured to maintain session stickiness, ensuring that requests from the same client are directed to the same backend instance. This is useful for applications that require session persistence.

6. Auto Scaling Integration: ELB works seamlessly with AWS Auto Scaling, allowing you to automatically add or remove instances based on traffic patterns. As traffic increases, new instances are added; when traffic decreases, instances are terminated.

7. Security Groups and Network ACLs: You can configure security groups and network ACLs to control inbound and outbound traffic to and from your instances behind the ELB.

8. Application Load Balancer (ALB): In addition to the classic Elastic Load Balancer, AWS offers the Application Load Balancer (ALB), which operates at the application layer (Layer 7) and provides advanced routing and content-based routing capabilities. ALB is suited for modern web applications.

---

### Availability, Scalability, Elasticity
**Availability** : Availability in the context of cloud computing, including AWS (Amazon Web Services), refers to the ability of a system, application, or service to remain operational and accessible to users without significant downtime or interruptions. AWS offers various features and services to help achieve high availability for applications and workloads hosted on its platform. 
Here are some key components and strategies related to availability in AWS:

1. Availability Zones (AZs): AWS has multiple data centers called Availability Zones (AZs) within each geographic region. AZs are physically isolated from one another and are designed to be independent of failures in other AZs. Distributing your resources across multiple AZs can improve your application's availability.

2. Regions: AWS Regions consist of multiple Availability Zones. Deploying your application in multiple regions provides even higher availability and disaster recovery capabilities. It's especially important for mission-critical applications.

3. Elastic Load Balancing (ELB): ELB automatically distributes incoming traffic across multiple instances or resources in different Availability Zones. This load balancing helps ensure that if one AZ experiences issues, traffic is redirected to healthy instances in other AZs.

4. Auto Scaling: AWS Auto Scaling allows you to automatically adjust the number of instances in response to changes in demand. This helps maintain consistent performance and availability, even during traffic spikes.

5. Multi-AZ Deployments: Deploying databases, such as Amazon RDS (Relational Database Service) and Amazon ElastiCache, in Multi-AZ mode ensures that your database instances have built-in failover capabilities and remain available even if one AZ becomes unavailable.

**Scalability** : Scalability is the ability of a system to handle an increasing amount of work, such as traffic, data, or user requests, by adding more resources (e.g., servers, storage, computing power) to the existing infrastructure. Scalability often requires manual intervention to add or remove resources. In traditional on-premises environments, this can be time-consuming and may lead to downtime during resource upgrades.

1. Types of Scalability:
- Vertical Scalability (Scaling Up): Increasing the capacity of existing resources by upgrading to more powerful hardware, such as adding more CPU, RAM, or storage to a single server or instance.
- Horizontal Scalability (Scaling Out): Adding more instances or servers to a system to distribute the workload. This can involve adding more virtual machines, containers, or microservices.

**Elasticity** : Elasticity is a specific aspect of scalability. It refers to the ability to automatically and dynamically allocate or deallocate resources in response to changing workloads, often based on defined policies or rules. Elasticity is automated and can be triggered by metrics like CPU utilization, incoming network traffic, or custom-defined thresholds. It ensures that resources are added or removed as needed without manual intervention.

#### Key Differences Between Scalability and Elasticity:

1. Automation: Scalability may involve manual intervention to add or remove resources, whereas elasticity is automated and responds to changes in demand automatically.

2. Response to Demand: Scalability doesn't necessarily respond in real-time to fluctuations in demand, whereas elasticity is designed to be responsive and dynamic.

3. Use Cases: Scalability is suited for scenarios with predictable resource needs, while elasticity is better for handling variable workloads and optimizing resource utilization and cost.

--- 

### Auto Scaling Groups (ASG)
In AWS (Amazon Web Services), an Auto Scaling Group (ASG) is a service that automatically adjusts the number of Amazon EC2 instances (virtual servers) in a group to maintain a desired level of availability and capacity. ASGs are a fundamental component of building scalable and fault-tolerant applications on AWS. Here's how Auto Scaling Groups work and why they are important:

Key Features and Concepts of Auto Scaling Groups:

1. Scaling Policies: ASGs are associated with scaling policies that define the conditions under which new instances are launched (scaling out) or existing instances are terminated (scaling in).

2. Desired Capacity: You specify the desired number of instances you want to maintain in the group. ASG continuously monitors this desired capacity and takes actions to maintain it.

3. Availability Zones: ASGs can span multiple Availability Zones (AZs) to ensure high availability. This helps distribute instances across physically separated data centers to reduce the risk of failures.

4. Launch Configurations or Launch Templates: To create instances in the group, you define a launch configuration or launch template. These templates specify instance types, AMIs (Amazon Machine Images), and other configuration settings.

5. Health Checks: ASGs regularly perform health checks on instances. If an instance fails a health check, the ASG can terminate it and launch a replacement to maintain the desired capacity.

6. Scaling Policies: Scaling policies can be based on various metrics, including CPU utilization, network traffic, or custom application-specific metrics. You can configure policies to scale based on these metrics.

7. Scheduled Scaling: You can configure scheduled scaling events to handle predictable changes in traffic, such as increased demand during business hours or decreased demand overnight.

8. Dynamic Scaling: ASGs can respond to sudden changes in demand by automatically adding or removing instances as needed. This ensures your application can handle varying workloads efficiently.

9. Lifecycle Hooks: ASGs support lifecycle hooks that allow you to perform custom actions during instance launch or termination. This can be useful for tasks like configuring instances before they enter service or cleaning up resources upon termination.

---

### Disaster Recovery (DR), Business Continuity Plan (BCP), Recovery Time Objective (RTO), Recovery Point Objective (RPO)
Disaster Recovery (DR): Ability to recover from a disaster and prevent the loss of data. (CloudEndure Disaster Recovery)

Business Continuity Plan (BCP) : A Business Continuity Plan (BCP) is a comprehensive strategy and set of procedures that an organization develops to ensure essential business functions can continue operating during and after a disruption or disaster. The primary goal of a BCP is to minimize downtime, maintain or quickly recover critical business operations, and minimize financial and operational losses in the face of unexpected events.

Recovery Time Objective (RTO) : RTO is the maximum acceptable amount of time it should take to restore a system, application, or service to normal operation after a disruption or disaster. It represents the target timeframe for recovery. 

Recovery Point Objective (RPO): RPO is the maximum allowable amount of data loss that an organization is willing to tolerate during a disruption or disaster. It defines the point in time to which data must be recovered in order to resume normal operations.

![](./imgs/dis_opt.png )

---

### Interact With AWS API Using : AWS Management Console, AWS SDK, AWS CLI
**AWS Management**: The AWS Management Console is a web-based user interface that provides a graphical way to access and manage AWS resources and services. It offers a user-friendly, point-and-click interface for performing tasks and configurations in AWS. It is ideal for users who prefer a visual and intuitive interface and it is useful for managing AWS resources and services through a web browser.

**AWS SDK**: Description: AWS SDKs are sets of libraries and tools provided by AWS to enable developers to interact programmatically with AWS services and resources. SDKs are available for various programming languages, including Python, Java, JavaScript, Ruby, and more. It is ideal for developers and software engineers who want to build applications that interact with AWS services and allows developers to integrate AWS services directly into their applications.

**AWS CLI**: WS CLI is a command-line tool that allows users to interact with AWS services and resources by running commands in a terminal or command prompt. It provides a text-based interface for managing AWS resources. It is ideal for users who prefer a command-line interface for scripting, automation, and managing AWS resources.

---

### Amazon Resource Name (ARN)
An Amazon Resource Name (ARN) is a unique identifier used in Amazon Web Services (AWS) to **reference and identify** AWS resources. ARNs are used across various AWS services and are used to specify the resource being accessed or acted upon in AWS APIs, policies, and configurations.

An ARN has a specific format:

```python
arn:aws:service:region:account-id:resource-type/resource-id
```

- **arn:** This is a constant that identifies the string as an ARN.
- **aws:** This field specifies that the resource is part of AWS.
- **service:** This field indicates the AWS service that the resource belongs to (e.g., s3 for Amazon S3, ec2 for Amazon EC2, lambda for AWS Lambda, etc.).
- **region:** This field specifies the AWS region where the resource is located. Not all resources are region-specific.
- **account-id**: This field represents the AWS account ID associated with the resource.
- **resource-type**: This field identifies the type of AWS resource (e.g., bucket for an Amazon S3 bucket, instance for an EC2 instance, function for a Lambda function, etc.).
- **resource-id:** This field uniquely identifies the specific resource within the AWS account and resource type.

Here are a few examples of ARNs for different AWS resources:
- Amazon S3 bucket: arn:aws:s3:::my-bucket (since S3 is a global service there is no reason to specify region or accound id)
- Amazon EC2 instance: arn:aws:ec2:us-east-1:123456789012:instance/i-12345678
- AWS Lambda function: arn:aws:lambda:us-west-2:9876543210:function:my-function

ARNs are used in various AWS contexts, including IAM (Identity and Access Management) policies, S3 bucket policies, CloudWatch alarms, and more. They help ensure that AWS resources are uniquely identifiable and can be referenced accurately in policies and configurations.

![](./imgs/arn.png)

---

### AWS Command Line Interface (CLI)
The AWS Command Line Interface (CLI) is a set of command-line tools provided by Amazon Web Services (AWS) to interact with and manage AWS resources and services from the command line of your local computer or a terminal. The AWS CLI offers a convenient and scriptable way to perform various AWS operations without the need for a graphical user interface. Here are some key aspects of the AWS CLI:

1. Installation: To use the AWS CLI, you need to install it on your local system. It's available for Windows, macOS, and Linux. You can download and install it from the AWS website or use package managers like pip on Linux. (AWS CLI is a Python executable program)

2. Configuration: After installation, you must configure the AWS CLI with your AWS access key ID, secret access key, default region, and other optional settings. You can configure it using the aws configure command or by editing the ~/.aws/config and ~/.aws/credentials files manually.

3. Command Structure: AWS CLI commands generally follow this structure: `aws <service> <operation> [options]`. For example, to list EC2 instances, you would use aws ec2 describe-instances.

4. Scripting and Automation: The AWS CLI is often used for scripting and automation tasks, as it can be easily integrated into scripts and workflows to automate AWS operations and manage resources programmatically.

5. Access Control:
    Access to AWS resources through the AWS CLI is controlled by AWS Identity and Access Management (IAM) policies associated with your AWS account. You can control who can perform actions using the CLI by creating and assigning IAM roles and policies.

6. Output Formats: The AWS CLI can display output in various formats, including JSON, text, and table. You can specify the desired output format using the --output option.

7. Subcommands and Options: AWS CLI commands are organized into services, subcommands, and options. You can use the --help option with any command or subcommand to display its documentation and available options.

8. Profile Management: You can configure multiple profiles in the AWS CLI, allowing you to switch between different AWS accounts and regions easily. Profiles are useful for managing resources across different AWS environments.

9. Integration with Other AWS Tools: The AWS CLI can be used in conjunction with other AWS tools and services, such as AWS CloudFormation, AWS Lambda, and AWS SDKs, to build and manage AWS resources and applications.

---

### Infrastructure as Code (IaC)
Infrastructure as Code (IaC) is a concept and practice in which infrastructure, including servers, networks, databases, and other resources, is provisioned and managed using code and automation scripts rather than manual processes. IaC allows you to define and describe your entire infrastructure as a set of code files that can be version-controlled, tested, and automated. It provides several benefits, including consistency, repeatability, and the ability to easily scale and manage infrastructure.

In AWS, IaC is commonly used to automate the provisioning and management of AWS resources and services. Here's how IaC works in AWS and some key tools and approaches associated with it:

1. Templates and Descriptions: In AWS, IaC is often implemented using templates or descriptions written in a domain-specific language. AWS provides two primary approaches for this: **AWS CloudFormation and AWS CDK (Cloud Development Kit).**

2. AWS CloudFormation: AWS CloudFormation is a service that allows you to define and provision AWS infrastructure as code using JSON or YAML templates. You describe the desired AWS resources and their configurations in the template, and CloudFormation handles the provisioning and management of those resources.

3. AWS CDK (Cloud Development Kit): AWS CDK is a more developer-friendly approach to IaC. It allows you to define infrastructure using programming languages like TypeScript, Python, Java, C#, and more. You write code to create and configure AWS resources, and the CDK generates CloudFormation templates under the hood.

4. Terraform: While not an AWS-specific tool, Terraform is another popular IaC tool used for managing infrastructure across multiple cloud providers, including AWS. Terraform uses its own language to describe infrastructure and provides a declarative approach to IaC.

![](./imgs/IaC.png)

#### AWS CloudFormation
AWS CloudFormation is a fully managed service provided by Amazon Web Services (AWS) that allows you to provision and manage AWS infrastructure and resources in a declarative and automated manner. CloudFormation uses templates to define the desired AWS resources and their configurations, enabling you to create, update, and delete resources as a single, coordinated stack.

Key features and concepts of AWS CloudFormation include:

1. Templates: CloudFormation templates are JSON or YAML files that define the AWS resources and their relationships. Templates can be version-controlled and shared among team members.

2. Declarative Language: You describe the desired state of your infrastructure in the template without specifying the step-by-step process to create it. CloudFormation handles the resource provisioning details.

3. Stacks: A stack is a set of AWS resources created and managed together as a single unit. Each CloudFormation template corresponds to a stack. Stacks can be created, updated, and deleted as a whole.

4. Resource Types: CloudFormation supports a wide range of AWS resource types, including EC2 instances, S3 buckets, RDS databases, Lambda functions, and more. You specify these resources in your template.

5. Parameters: Templates can include parameters, allowing you to customize resource configurations during stack creation. Parameters make templates reusable for different environments or use cases.

6. Outputs: You can define outputs in your CloudFormation template to expose specific resource attributes. This is useful for extracting information about the created resources, such as IP addresses or ARNs.

7. Mappings and Conditions: CloudFormation templates support mappings and conditions, which allow you to define conditional resource creation and resource attributes based on input parameters or conditions.

8. Nested Stacks: You can use nested stacks to create modular and reusable templates. A parent stack can include one or more nested stacks, allowing you to break down complex infrastructures into manageable components.

9. Change Sets: Before making changes to an existing stack, CloudFormation allows you to preview those changes using change sets. This helps you understand the impact of proposed updates.

10. Rollbacks: CloudFormation provides automatic rollback mechanisms in case of stack creation or update failures, ensuring that your infrastructure remains in a consistent state.

11. Integration with AWS Services: CloudFormation integrates with various AWS services and features, such as AWS Identity and Access Management (IAM) for security, AWS CloudTrail for auditing, and AWS Systems Manager for automation.

12. AWS CloudFormation Registry: The AWS CloudFormation Registry allows you to create and publish custom resource types (formerly known as AWS CloudFormation Macros) and modules to extend CloudFormation's capabilities.

![](./imgs/cloudformation.png)

#### Cloud Development Kit (CDK)
The AWS Cloud Development Kit (CDK) is an open-source software development framework developed by Amazon Web Services (AWS) that allows developers to define cloud infrastructure using familiar programming languages. CDK enables you to create and manage AWS resources and services using languages like TypeScript, Python, Java, C#, and others, instead of writing traditional CloudFormation templates in JSON or YAML.

Key features and concepts of the AWS CDK include:

1. Familiar Programming Languages: With CDK, you can use programming languages you already know, such as TypeScript, Python, Java, and C#, to define AWS infrastructure, making it more accessible to developers.

2. Constructs: CDK defines reusable building blocks called "constructs" that represent AWS resources or groups of resources. For example, there are constructs for EC2 instances, S3 buckets, Lambda functions, and more.

3. Staging and Synthesis: CDK provides a staging and synthesis process that converts your code into CloudFormation templates for deployment. The cdk deploy command deploys your infrastructure based on the CDK code.

4. High-Level Abstractions: CDK includes high-level abstractions that simplify the definition of complex AWS resources. For instance, you can create an Amazon S3 bucket with a single line of code instead of specifying the details in a CloudFormation template.

5. Language-Specific Libraries: CDK offers language-specific libraries and modules for AWS services, allowing you to use familiar objects and methods to configure and interact with AWS resources.

6. Automatic Dependency Management: CDK automatically manages dependencies between resources and ensures that resources are created in the correct order during deployment.

7. Custom Constructs: You can create custom constructs to encapsulate common patterns or resource configurations specific to your applications or organization.

8. CDK Apps: CDK apps are projects or applications built using CDK constructs. An app can define one or more stacks, which represent sets of AWS resources.

9. AWS Integration: CDK integrates with AWS services like AWS Lambda for custom resource provisioning and AWS Identity and Access Management (IAM) for security configuration.

10. Cross-Account and Cross-Region Deployment: CDK allows you to deploy infrastructure across AWS accounts and regions, making it suitable for complex multi-account or multi-region architectures.

11. CDK Pipelines: AWS CDK Pipelines is an extension of CDK that enables you to define and deploy continuous delivery pipelines for your CDK applications using AWS CodePipeline.

![](./imgs/cdk.png)

---

### AWS Access Keys
Access Keys is a key and secret required to have programmatic access to AWS resources when interacting with the AWS API outside the AWS Management Console. An Access Key is commonly referred to as AWS Credentials. It consist of an Access Key ID and a Secret Access Key : 

- Access Key ID: The Access Key ID is a public identifier that AWS uses to associate requests with your AWS account. It is a unique alphanumeric string, like "AKIAIOSFODNN7EXAMPLE," and it is not considered sensitive information. The Access Key ID is included in API requests and is used by AWS to identify the requester.

- Secret Access Key: The Secret Access Key is a private, confidential key associated with the Access Key ID. It is a long, randomly generated alphanumeric string, like "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY." The Secret Access Key must be kept confidential and should not be shared or exposed. It is used to sign API requests, providing proof that the requestor possesses the corresponding Access Key ID and the Secret Access Key.

![](./imgs/acc_key.png)

![](./imgs/acc_key2.png)