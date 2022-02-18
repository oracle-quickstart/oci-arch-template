

> # Reference Architecture Standards
>
 |Info - Instructions to use this template                            | 
|-------------------------------------------------|
| - Give your reference architecture a short and business-focused title (*example: _Build a SIEM system in Splunk using logs streamed from Oracle Cloud*).  |
|  -  Follow the instructions provided within each section of this template. Remove the instructions when you're done.|
|  -   Focus on technical accuracy and completeness. Before your content is published externally, it will be reviewed and scrubbed thoroughly for language, style, and formatting. |
| -   **DO NOT copy content from any non-Oracle source, unless you've obtained explicit permission to reuse content from the copyright owner. If you have permission from a third-party copyright owner to reuse content, then DO cite the third-party source and include the evidence of explicit permission to reuse that content.**  |
||

**Status**: > *In progress | Ready for publishing | Archived*

**Metadata**
**Filters - technology**  
*Compute, Database, Terraform*

**Filters - products and services** (a maximum of 6 products)
*Cloud Infrastructure, Compute, Database, MySQL, MySQL Database, Linux, Load Balancing*

**Filters - Industry**
*Life Science*

# **Overview**

> *Don't change the section title! Write a brief overview of the business or technical goal of the reference architecture.*

# Architecture

> *Don't change the section title! In one or two short paragraphs, describe the architecture at a high level.*

The following diagram illustrates this reference architecture.

> *Insert a sketch of the architecture diagram here.*

> *The sketch can be rough. Use any tool of your choice. Draw.io is ideal, because it supports in-place editing within Confluence wiki pages. Feel free to use Visio, PowerPoint, or any other tool.*

> *You can use the templates and icons available here: https://docs.cloud.oracle.com/en-us/iaas/Content/General/Reference/graphicsfordiagrams.htm#Graphics_for_Topologies_and_Diagrams.*

> *Drawio versions of the latest architectures published are also available in [Reference Architecture Center](https://docs.oracle.com/solutions/)   These might be useful if you prefer a “starter” image that you can customize/edit.*

This architecture has the following components:

> *Describe the key components of the architecture. The bullets listed in the template are boilerplate that you can use if the component is in your architecture. Add descriptions and components as needed.*

-   **Tenancy**

Oracle Autonomous Transaction Processing is a self-driving, self-securing, self-repairing database service that is optimized for transaction processing workloads. You do not need to configure or manage any hardware, or install any software. Oracle Cloud Infrastructure handles creating the database, as well as backing up, patching, upgrading, and tuning the database.

-   **Region**

An Oracle Cloud Infrastructure region is a localized geographic area that contains one or more data centers, called availability domains. Regions are independent of other regions, and vast distances can separate them (across countries or even continents).

-   **Compartment**

Compartments are cross-region logical partitions within an Oracle Cloud Infrastructure tenancy. Use compartments to organize your resources in Oracle Cloud, control access to the resources, and set usage quotas. To control access to the resources in a given compartment, you define policies that specify who can access the resources and what actions they can perform..

-   **Availability domains**

Availability domains are standalone, independent data centers within a region. The physical resources in each availability domain are isolated from the resources in the other availability domains, which provides fault tolerance. Availability domains don’t share infrastructure such as power or cooling, or the internal availability domain network. So, a failure at one availability domain is unlikely to affect the other availability domains in the region.

-   **Fault domains**

A fault domain is a grouping of hardware and infrastructure within an availability domain. Each availability domain has three fault domains with independent power and hardware. When you distribute resources across multiple fault domains, your applications can tolerate physical server failure, system maintenance, and power failures inside a fault domain.

-   **Virtual cloud network (VCN) and subnets**

A VCN is a customizable, software-defined network that you set up in an Oracle Cloud Infrastructure region. Like traditional data center networks, VCNs give you complete control over your network environment. A VCN can have multiple non-overlapping CIDR blocks that you can change after you create the VCN. You can segment a VCN into subnets, which can be scoped to a region or to an availability domain. Each subnet consists of a contiguous range of addresses that don't overlap with the other subnets in the VCN. You can change the size of a subnet after creation. A subnet can be public or private.

-   **Load balancer**

The Oracle Cloud Infrastructure Load Balancing service provides automated traffic distribution from a single entry point to multiple servers in the back end.

The load balancer provides access to different applications.

-   **Security list**

For each subnet, you can create security rules that specify the source, destination, and type of traffic that must be allowed in and out of the subnet.

-   **NAT gateway**

The NAT gateway enables private resources in a VCN to access hosts on the internet, without exposing those resources to incoming internet connections.

-   **Service gateway**

The service gateway provides access from a VCN to other services, such as Oracle Cloud Infrastructure Object Storage. The traffic from the VCN to the Oracle service travels over the Oracle network fabric and never traverses the internet.

-   **Cloud Guard**

You can use Oracle Cloud Guard to monitor and maintain the security of your resources in Oracle Cloud Infrastructure. Cloud Guard uses detector recipes that you can define to examine your resources for security weaknesses and to monitor operators and users for risky activities. When any misconfiguration or insecure activity is detected, Cloud Guard recommends corrective actions and assists with taking those actions, based on responder recipes that you can define.

-   **Security zone**

Security zones ensure Oracle's security best practices from the start by enforcing policies such as encrypting data and preventing public access to networks for an entire compartment. A security zone is associated with a compartment of the same name and includes security zone policies or a "recipe" that applies to the compartment and its sub-compartments. You can't add or move a standard compartment to a security zone compartment.

-   **Object storage**

Object storage provides quick access to large amounts of structured and unstructured data of any content type, including database backups, analytic data, and rich content such as images and videos. You can safely and securely store and then retrieve data directly from the internet or from within the cloud platform. You can seamlessly scale storage without experiencing any degradation in performance or service reliability. Use standard storage for "hot" storage that you need to access quickly, immediately, and frequently. Use archive storage for "cold" storage that you retain for long periods of time and seldom or rarely access.

-   **FastConnect**

Oracle Cloud Infrastructure FastConnect provides an easy way to create a dedicated, private connection between your data center and Oracle Cloud Infrastructure. FastConnect provides higher-bandwidth options and a more reliable networking experience when compared with internet-based connections.

-   **Local peering gateway (LPG)**

An LPG enables you to peer one VCN with another VCN in the same region. Peering means the VCNs communicate using private IP addresses, without the traffic traversing the internet or routing through your on-premises network.

-   **Autonomous database**

Oracle Cloud Infrastructure autonomous databases are fully managed, preconfigured database environments that you can use for transaction processing and data warehousing workloads. You do not need to configure or manage any hardware, or install any software. Oracle Cloud Infrastructure handles creating the database, as well as backing up, patching, upgrading, and tuning the database.

-   **Autonomous Data Warehouse**

Oracle Autonomous Data Warehouse is a self-driving, self-securing, self-repairing database service that is optimized for data warehousing workloads. You do not need to configure or manage any hardware, or install any software. Oracle Cloud Infrastructure handles creating the database, as well as backing up, patching, upgrading, and tuning the database.

-   **Autonomous Transaction Processing**

Oracle Autonomous Transaction Processing is a self-driving, self-securing, self-repairing database service that is optimized for transaction processing workloads. You do not need to configure or manage any hardware, or install any software. Oracle Cloud Infrastructure handles creating the database, as well as backing up, patching, upgrading, and tuning the database.

-   **Exadata DB system**

Exadata Cloud Service enables you to leverage the power of Exadata in the cloud. You can provision flexible X8M systems that allow you to add database compute servers and storage servers to your system as your needs grow. X8M systems offer RoCE (RDMA over Converged Ethernet) networking for high bandwidth and low latency, persistent memory (PMEM) modules, and intelligent Exadata software. You can provision X8M systems by using a shape that's equivalent to a quarter-rack X8 system, and then add database and storage servers at any time after provisioning.

-   Component

Description

# Recommendations

Use the following recommendations as a starting point. Your requirements might differ.

> *Use a bullet list to provide recommendations.*

-   **VCN**

The following are sample recommendations. If any of these aren't relevant to your reference architecture, remove them.

When you create a VCN, determine the number of CIDR blocks required and the size of each block based on the number of resources that you plan to attach to subnets in the VCN. Use CIDR blocks that are within the standard private IP address space.

Select CIDR blocks that don't overlap with any other network (in Oracle Cloud Infrastructure, your on-premises data center, or another cloud provider) to which you intend to set up private connections.

After you create a VCN, you can change, add, and remove its CIDR blocks.

When you design the subnets, consider your traffic flow and security requirements. Attach all the resources within a specific tier or role to the same subnet, which can serve as a security boundary.

Use regional subnets.

-   **Security  
    **

The following is an Oracle-recommended best practice. Don't remove it.

Use Oracle Cloud Guard to monitor and maintain the security of your resources in Oracle Cloud Infrastructure proactively. Cloud Guard uses detector recipes that you can define to examine your resources for security weaknesses and to monitor operators and users for risky activities. When any misconfiguration or insecure activity is detected, Cloud Guard recommends corrective actions and assists with taking those actions, based on responder recipes that you can define.

For resources that require maximum security, Oracle recommends that you use security zones. A security zone is a compartment associated with an Oracle-defined recipe of security policies that are based on best practices. For example, the resources in a security zone must not be accessible from the public internet and they must be encrypted using customer-managed keys. When you create and update resources in a security zone, Oracle Cloud Infrastructure validates the operations against the policies in the security-zone recipe, and denies operations that violate any of the policies.

-   **Cloud Guard  
    **The following is an Oracle-recommended best practice. Don't remove it.

Clone and customize the default recipes provided by Oracle to create custom detector and responder recipes. These recipes enable you to specify what type of security violations generate a warning and what actions are allowed to be performed on them. For example, you might want to detect Object Storage buckets that have visibility set to public.

Apply Cloud Guard at the tenancy level to cover the broadest scope and to reduce the administrative burden of maintaining multiple configurations.

You can also use the Managed List feature to apply certain configurations to detectors.

-   **Security zones**

Clone and customize the default recipes provided by Oracle to create custom detector and responder recipes. These recipes enable you to specify what type of security violations generate a warning and what actions are allowed to be performed on them. For example, you might want to detect Object Storage buckets that have visibility set to public.

Apply Cloud Guard at the tenancy level to cover the broadest scope and to reduce the administrative burden of maintaining multiple configurations.

You can also use the Managed List feature to apply certain configurations to detectors.

-   **Network security groups (NSGs)**

You can use NSGs to define a set of ingress and egress rules that apply to specific VNICs. We recommend using NSGs rather than security lists, because NSGs enable you to separate the VCN's subnet architecture from the security requirements of your application.

You can use NSGs to define a set of ingress and egress rules that apply to specific VNICs. We recommend using NSGs rather than security lists, because NSGs enable you to separate the VCN's subnet architecture from the security requirements of your application.

-   **Load balancer bandwidth**

While creating the load balancer, you can either select a predefined shape that provides a fixed bandwidth, or specify a custom (flexible) shape where you set a bandwidth range and let the service scale the bandwidth automatically based on traffic patterns. With either approach, you can change the shape at any time after creating the load balancer.

> -   *Component/Topic*

> *Description*

# Considerations

Consider the following points when deploying this reference architecture.

> *Use a bullet list to provide considerations. The following bullets show examples of the kinds of considerations that you might describe. If this text is not relevant for your architecture, delete it and enter relevant content*

-   **Performance**

> *Description*

-   **Security**

> *Description*

-   **Availability**

> *Description*

-   **Cost**

> *Description*

-   **Factor**

> *Description*

# Deploy

> *_Answer the following question. The writer assigned to this reference architecture will review the answer, and work with you to develop the deployment instructions._

How can customers deploy this reference architecture?

-   Using an Oracle Cloud marketplace stack or image: <link to marketplace listing>. If the listing is not public yet, what is the target release date?
-   Using Oracle-approved code on GitHub: <link to repo on GitHub>. If the code is not public yet, what is the target release date?
-   Using manual steps published elsewhere in official Oracle documentation: <link to doc>. If the doc is not public yet, what is the target release date?
-   Using a solution playbook that's being developed (<name of playbook developer>, <target release date>).
-   Other method (describe it briefly).
-   This reference architecture provides only the design. We don't have a deployment method at this time.

# Explore More

To learn more about *topics/s*, see the following resources:

> *Use a bullet list to provide links to relevant resources. Type the title of the resource, and use that text as the link text, as shown in the following examples. DO NOT link to blogs and other "community" content. Link to only the relevant and essential resources.*

-   [Best practices framework for Oracle Cloud Infrastructure](https://docs.oracle.com/en/solutions/oci-best-practices/index.html)
    
-   <link>
-   <link>

# Acknowledgements

-   Authors:  
> *Anyone who wrote at least 25% of the content, or was a key contributor. A key contributor is someone whose talents, knowledge, or participation made the article possible. A key contributor might have written less than 25%, but without their participation the article wouldn't exist.*
-   Contributors:  
> *Optionally, list one or more Contributors. Anyone who wrote some, but less than 25% of the content, or anyone responsible for the technical accuracy of the content, such as the primary technical reviewer or someone who validated the architecture.*


