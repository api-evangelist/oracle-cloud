# Oracle Cloud Infrastructure (oracle-cloud)
Collection of Oracle Cloud Infrastructure (OCI) REST APIs for managing cloud resources and services.

**URL:** [https://raw.githubusercontent.com/api-evangelist/oracle-cloud/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/oracle-cloud/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Cloud Computing, Enterprise Cloud, Infrastructure as a Service, Oracle, Platform as a Service

## Timestamps

- **Created:** 2024-01-01
- **Modified:** 2026-04-18

## APIs

### Compute API
Manage compute instances, images, and related resources.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/iaas/latest/Instance/](https://docs.oracle.com/en-us/iaas/api/#/en/iaas/latest/Instance/)

#### Tags:

 - Compute, Instances, Virtual Machines

#### Properties

- [OpenAPI](openapi/oracle-cloud-compute-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/Compute/home.htm)
- [Pricing](https://www.oracle.com/cloud/compute/pricing.html)
- [JSONSchema](json-schema/compute-update-instance-details-schema.json)
- [JSONSchema](json-schema/compute-volume-attachment-schema.json)
- [JSONSchema](json-schema/compute-shape-schema.json)
- [JSONSchema](json-schema/compute-image-schema.json)
- [JSONSchema](json-schema/compute-instance-schema.json)
- [JSONSchema](json-schema/compute-launch-instance-details-schema.json)
- [JSONSchema](json-schema/compute-attach-volume-details-schema.json)
- [JSONStructure](json-structure/compute-volume-attachment-structure.json)
- [JSONStructure](json-structure/compute-launch-instance-details-structure.json)
- [JSONStructure](json-structure/compute-image-structure.json)
- [JSONStructure](json-structure/compute-shape-structure.json)
- [JSONStructure](json-structure/compute-instance-structure.json)
- [JSONStructure](json-structure/compute-update-instance-details-structure.json)
- [JSONStructure](json-structure/compute-attach-volume-details-structure.json)
- [Example](examples/compute-volume-attachment-example.json)
- [Example](examples/compute-shape-example.json)
- [Example](examples/compute-image-example.json)
- [Example](examples/compute-instance-example.json)
- [Example](examples/compute-update-instance-details-example.json)
- [Example](examples/compute-attach-volume-details-example.json)
- [Example](examples/compute-launch-instance-details-example.json)

### Object Storage API
Store and retrieve large amounts of unstructured data.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/objectstorage/latest/](https://docs.oracle.com/en-us/iaas/api/#/en/objectstorage/latest/)

#### Tags:

 - Buckets, Object Storage, Storage

#### Properties

- [OpenAPI](openapi/oracle-cloud-object-storage-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/Object/home.htm)
- [Pricing](https://www.oracle.com/cloud/storage/pricing.html)
- [JSONSchema](json-schema/object-storage-object-summary-schema.json)
- [JSONSchema](json-schema/object-storage-bucket-summary-schema.json)
- [JSONSchema](json-schema/object-storage-update-bucket-details-schema.json)
- [JSONSchema](json-schema/object-storage-preauthenticated-request-summary-schema.json)
- [JSONSchema](json-schema/object-storage-preauthenticated-request-schema.json)
- [JSONSchema](json-schema/object-storage-bucket-schema.json)
- [JSONSchema](json-schema/object-storage-list-objects-schema.json)
- [JSONSchema](json-schema/object-storage-create-bucket-details-schema.json)
- [JSONSchema](json-schema/object-storage-create-preauthenticated-request-details-schema.json)
- [JSONStructure](json-structure/object-storage-create-bucket-details-structure.json)
- [JSONStructure](json-structure/object-storage-create-preauthenticated-request-details-structure.json)
- [JSONStructure](json-structure/object-storage-update-bucket-details-structure.json)
- [JSONStructure](json-structure/object-storage-object-summary-structure.json)
- [JSONStructure](json-structure/object-storage-list-objects-structure.json)
- [JSONStructure](json-structure/object-storage-preauthenticated-request-summary-structure.json)
- [JSONStructure](json-structure/object-storage-preauthenticated-request-structure.json)
- [JSONStructure](json-structure/object-storage-bucket-summary-structure.json)
- [JSONStructure](json-structure/object-storage-bucket-structure.json)
- [Example](examples/object-storage-preauthenticated-request-example.json)
- [Example](examples/object-storage-bucket-example.json)
- [Example](examples/object-storage-bucket-summary-example.json)
- [Example](examples/object-storage-preauthenticated-request-summary-example.json)
- [Example](examples/object-storage-list-objects-example.json)
- [Example](examples/object-storage-create-bucket-details-example.json)
- [Example](examples/object-storage-object-summary-example.json)
- [Example](examples/object-storage-create-preauthenticated-request-details-example.json)
- [Example](examples/object-storage-update-bucket-details-example.json)

### Networking API
Manage virtual cloud networks, subnets, and network resources.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/iaas/latest/Vcn/](https://docs.oracle.com/en-us/iaas/api/#/en/iaas/latest/Vcn/)

#### Tags:

 - Load Balancer, Networking, VCN

#### Properties

- [OpenAPI](openapi/oracle-cloud-networking-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/overview.htm)
- [JSONSchema](json-schema/networking-vcn-schema.json)
- [JSONSchema](json-schema/networking-create-vcn-details-schema.json)
- [JSONSchema](json-schema/networking-create-subnet-details-schema.json)
- [JSONSchema](json-schema/networking-route-table-schema.json)
- [JSONSchema](json-schema/networking-update-vcn-details-schema.json)
- [JSONSchema](json-schema/networking-create-internet-gateway-details-schema.json)
- [JSONSchema](json-schema/networking-subnet-schema.json)
- [JSONSchema](json-schema/networking-internet-gateway-schema.json)
- [JSONSchema](json-schema/networking-security-list-schema.json)
- [JSONStructure](json-structure/networking-security-list-structure.json)
- [JSONStructure](json-structure/networking-route-table-structure.json)
- [JSONStructure](json-structure/networking-update-vcn-details-structure.json)
- [JSONStructure](json-structure/networking-subnet-structure.json)
- [JSONStructure](json-structure/networking-create-subnet-details-structure.json)
- [JSONStructure](json-structure/networking-create-internet-gateway-details-structure.json)
- [JSONStructure](json-structure/networking-vcn-structure.json)
- [JSONStructure](json-structure/networking-internet-gateway-structure.json)
- [JSONStructure](json-structure/networking-create-vcn-details-structure.json)
- [Example](examples/networking-create-internet-gateway-details-example.json)
- [Example](examples/networking-security-list-example.json)
- [Example](examples/networking-internet-gateway-example.json)
- [Example](examples/networking-update-vcn-details-example.json)
- [Example](examples/networking-vcn-example.json)
- [Example](examples/networking-create-vcn-details-example.json)
- [Example](examples/networking-subnet-example.json)
- [Example](examples/networking-create-subnet-details-example.json)
- [Example](examples/networking-route-table-example.json)

### Database API
Manage Oracle Database Cloud Services and Autonomous Databases.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/database/latest/](https://docs.oracle.com/en-us/iaas/api/#/en/database/latest/)

#### Tags:

 - Autonomous Database, Database, DBaaS

#### Properties

- [OpenAPI](openapi/oracle-cloud-database-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/Database/home.htm)
- [Pricing](https://www.oracle.com/cloud/price-list.html#database)
- [JSONSchema](json-schema/database-update-autonomous-database-details-schema.json)
- [JSONSchema](json-schema/database-autonomous-database-schema.json)
- [JSONSchema](json-schema/database-db-system-schema.json)
- [JSONSchema](json-schema/database-create-autonomous-database-details-schema.json)
- [JSONSchema](json-schema/database-autonomous-database-summary-schema.json)
- [JSONSchema](json-schema/database-db-system-summary-schema.json)
- [JSONStructure](json-structure/database-create-autonomous-database-details-structure.json)
- [JSONStructure](json-structure/database-autonomous-database-summary-structure.json)
- [JSONStructure](json-structure/database-update-autonomous-database-details-structure.json)
- [JSONStructure](json-structure/database-db-system-structure.json)
- [JSONStructure](json-structure/database-autonomous-database-structure.json)
- [JSONStructure](json-structure/database-db-system-summary-structure.json)
- [Example](examples/database-db-system-summary-example.json)
- [Example](examples/database-update-autonomous-database-details-example.json)
- [Example](examples/database-create-autonomous-database-details-example.json)
- [Example](examples/database-autonomous-database-example.json)
- [Example](examples/database-db-system-example.json)
- [Example](examples/database-autonomous-database-summary-example.json)

### Identity and Access Management API
Manage users, groups, policies, and authentication.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/identity/latest/](https://docs.oracle.com/en-us/iaas/api/#/en/identity/latest/)

#### Tags:

 - Authentication, Authorization, IAM, Security

#### Properties

- [OpenAPI](openapi/oracle-cloud-iam-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/Identity/home.htm)
- [JSONSchema](json-schema/iam-policy-schema.json)
- [JSONSchema](json-schema/iam-compartment-schema.json)
- [JSONSchema](json-schema/iam-create-policy-details-schema.json)
- [JSONSchema](json-schema/iam-create-user-details-schema.json)
- [JSONSchema](json-schema/iam-group-schema.json)
- [JSONSchema](json-schema/iam-update-user-details-schema.json)
- [JSONSchema](json-schema/iam-create-group-details-schema.json)
- [JSONSchema](json-schema/iam-user-schema.json)
- [JSONStructure](json-structure/iam-create-group-details-structure.json)
- [JSONStructure](json-structure/iam-policy-structure.json)
- [JSONStructure](json-structure/iam-create-user-details-structure.json)
- [JSONStructure](json-structure/iam-compartment-structure.json)
- [JSONStructure](json-structure/iam-update-user-details-structure.json)
- [JSONStructure](json-structure/iam-create-policy-details-structure.json)
- [JSONStructure](json-structure/iam-user-structure.json)
- [JSONStructure](json-structure/iam-group-structure.json)
- [Example](examples/iam-policy-example.json)
- [Example](examples/iam-create-policy-details-example.json)
- [Example](examples/iam-create-group-details-example.json)
- [Example](examples/iam-group-example.json)
- [Example](examples/iam-create-user-details-example.json)
- [Example](examples/iam-compartment-example.json)
- [Example](examples/iam-update-user-details-example.json)
- [Example](examples/iam-user-example.json)

### Container Engine for Kubernetes API
Manage Kubernetes clusters and node pools.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/containerengine/latest/](https://docs.oracle.com/en-us/iaas/api/#/en/containerengine/latest/)

#### Tags:

 - Containers, Kubernetes, OKE

#### Properties

- [OpenAPI](openapi/oracle-cloud-oke-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/ContEng/home.htm)
- [JSONSchema](json-schema/oke-node-pool-schema.json)
- [JSONSchema](json-schema/oke-node-pool-summary-schema.json)
- [JSONSchema](json-schema/oke-create-cluster-details-schema.json)
- [JSONSchema](json-schema/oke-create-node-pool-details-schema.json)
- [JSONSchema](json-schema/oke-update-cluster-details-schema.json)
- [JSONSchema](json-schema/oke-cluster-summary-schema.json)
- [JSONSchema](json-schema/oke-cluster-schema.json)
- [JSONStructure](json-structure/oke-cluster-structure.json)
- [JSONStructure](json-structure/oke-node-pool-summary-structure.json)
- [JSONStructure](json-structure/oke-update-cluster-details-structure.json)
- [JSONStructure](json-structure/oke-create-node-pool-details-structure.json)
- [JSONStructure](json-structure/oke-node-pool-structure.json)
- [JSONStructure](json-structure/oke-create-cluster-details-structure.json)
- [JSONStructure](json-structure/oke-cluster-summary-structure.json)
- [Example](examples/oke-cluster-summary-example.json)
- [Example](examples/oke-create-cluster-details-example.json)
- [Example](examples/oke-cluster-example.json)
- [Example](examples/oke-node-pool-example.json)
- [Example](examples/oke-update-cluster-details-example.json)
- [Example](examples/oke-node-pool-summary-example.json)
- [Example](examples/oke-create-node-pool-details-example.json)

### Functions API
Serverless platform for building and running applications.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/functions/latest/](https://docs.oracle.com/en-us/iaas/api/#/en/functions/latest/)

#### Tags:

 - FaaS, Functions, Serverless

#### Properties

- [OpenAPI](openapi/oracle-cloud-functions-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/Functions/home.htm)
- [JSONSchema](json-schema/functions-create-function-details-schema.json)
- [JSONSchema](json-schema/functions-create-application-details-schema.json)
- [JSONSchema](json-schema/functions-application-summary-schema.json)
- [JSONSchema](json-schema/functions-function-summary-schema.json)
- [JSONSchema](json-schema/functions-function-schema.json)
- [JSONSchema](json-schema/functions-application-schema.json)
- [JSONStructure](json-structure/functions-function-summary-structure.json)
- [JSONStructure](json-structure/functions-application-structure.json)
- [JSONStructure](json-structure/functions-create-function-details-structure.json)
- [JSONStructure](json-structure/functions-create-application-details-structure.json)
- [JSONStructure](json-structure/functions-application-summary-structure.json)
- [JSONStructure](json-structure/functions-function-structure.json)
- [Example](examples/functions-application-example.json)
- [Example](examples/functions-function-example.json)
- [Example](examples/functions-create-function-details-example.json)
- [Example](examples/functions-create-application-details-example.json)
- [Example](examples/functions-application-summary-example.json)
- [Example](examples/functions-function-summary-example.json)

### Monitoring API
Monitor cloud resources using metrics and alarms.

**Human URL:** [https://docs.oracle.com/en-us/iaas/api/#/en/monitoring/latest/](https://docs.oracle.com/en-us/iaas/api/#/en/monitoring/latest/)

#### Tags:

 - Alarms, Metrics, Monitoring

#### Properties

- [OpenAPI](openapi/oracle-cloud-monitoring-openapi.yaml)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/Monitoring/home.htm)
- [JSONSchema](json-schema/monitoring-metric-data-schema.json)
- [JSONSchema](json-schema/monitoring-create-alarm-details-schema.json)
- [JSONSchema](json-schema/monitoring-update-alarm-details-schema.json)
- [JSONSchema](json-schema/monitoring-summarize-metrics-data-details-schema.json)
- [JSONSchema](json-schema/monitoring-metric-schema.json)
- [JSONSchema](json-schema/monitoring-alarm-schema.json)
- [JSONSchema](json-schema/monitoring-alarm-summary-schema.json)
- [JSONStructure](json-structure/monitoring-summarize-metrics-data-details-structure.json)
- [JSONStructure](json-structure/monitoring-create-alarm-details-structure.json)
- [JSONStructure](json-structure/monitoring-alarm-structure.json)
- [JSONStructure](json-structure/monitoring-update-alarm-details-structure.json)
- [JSONStructure](json-structure/monitoring-metric-data-structure.json)
- [JSONStructure](json-structure/monitoring-alarm-summary-structure.json)
- [JSONStructure](json-structure/monitoring-metric-structure.json)
- [Example](examples/monitoring-alarm-example.json)
- [Example](examples/monitoring-metric-data-example.json)
- [Example](examples/monitoring-create-alarm-details-example.json)
- [Example](examples/monitoring-update-alarm-details-example.json)
- [Example](examples/monitoring-alarm-summary-example.json)
- [Example](examples/monitoring-summarize-metrics-data-details-example.json)
- [Example](examples/monitoring-metric-example.json)

## Common Properties

- [Portal](https://cloud.oracle.com/)
- [Console](https://console.oracle.com/)
- [Documentation](https://docs.oracle.com/en-us/iaas/Content/home.htm)
- [Authentication](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/sdk_authentication_methods.htm)
- [SDK](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/sdks.htm)
- [CLI](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cliconcepts.htm)
- [StatusPage](https://ocistatus.oraclecloud.com/)
- [Support](https://www.oracle.com/support/)
- [Pricing](https://www.oracle.com/cloud/price-list.html)
- [TermsOfService](https://www.oracle.com/legal/terms.html)
- [PrivacyPolicy](https://www.oracle.com/legal/privacy/)
- [GettingStarted](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/baremetalintro.htm)
- [Blog](https://blogs.oracle.com/cloud-infrastructure/)
- [GitHubOrganization](https://github.com/oracle)
- [ReleaseNotes](https://docs.oracle.com/en-us/iaas/releasenotes/index.htm)
- [SignUp](https://www.oracle.com/cloud/free/)
- [Training](https://www.oracle.com/cloud/training/)
- [ChangeLog](https://docs.oracle.com/en-us/iaas/Content/servicechanges.htm)
- [SDK (Java SDK)](https://github.com/oracle/oci-java-sdk)
- [SDK (Python SDK)](https://github.com/oracle/oci-python-sdk)
- [SDK (TypeScript SDK)](https://github.com/oracle/oci-typescript-sdk)
- [SDK (.NET SDK)](https://github.com/oracle/oci-dotnet-sdk)
- [SDK (Go SDK)](https://github.com/oracle/oci-go-sdk)
- [SDK (Ruby SDK)](https://github.com/oracle/oci-ruby-sdk)
- [SDK (PowerShell Modules)](https://github.com/oracle/oci-powershell-modules)
- [GitHubRepository (OCI CLI Repository)](https://github.com/oracle/oci-cli)
- [GitHubRepository (Terraform Provider)](https://github.com/oracle/terraform-provider-oci)
- [SpectralRules](rules/oracle-cloud-spectral-rules.yml)
- [Vocabulary](vocabulary/oracle-cloud-vocabulary.yaml)
- [NaftikoCapability](capabilities/data-platform.yaml)
- [NaftikoCapability](capabilities/cloud-native-development.yaml)
- [NaftikoCapability](capabilities/infrastructure-management.yaml)
- [NaftikoCapability](capabilities/security-and-compliance.yaml)
- [JSONLD](json-ld/oracle-cloud-iam-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-database-create-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-monitoring-summarize-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-iam-update-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-oke-create-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-oke-node-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-functions-function-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-networking-update-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-database-db-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-functions-application-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-functions-create-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-object-storage-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-compute-update-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-database-autonomous-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-oke-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-monitoring-update-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-networking-route-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-compute-launch-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-compute-volume-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-monitoring-create-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-monitoring-metric-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-compute-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-functions-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-oke-cluster-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-networking-internet-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-monitoring-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-compute-attach-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-iam-create-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-database-update-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-networking-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-networking-create-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-oke-update-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-networking-security-context.jsonld)
- [JSONLD](json-ld/oracle-cloud-monitoring-alarm-context.jsonld)

## Features

| Name | Description |
|------|-------------|
| Compute | Bare metal, virtual machine, and GPU compute instances with flexible shapes and autoscaling |
| Object Storage | Highly durable and scalable object storage for unstructured data with S3 compatibility |
| Autonomous Database | Self-driving, self-securing, self-repairing database with automated patching and tuning |
| Container Engine for Kubernetes | Managed Kubernetes service for deploying and managing containerized applications |
| Virtual Cloud Networks | Software-defined networking with private subnets, security lists, and network security groups |
| Identity and Access Management | Fine-grained access control with policies, compartments, and identity federation |
| Serverless Functions | Event-driven serverless compute platform based on Fn Project |
| Load Balancing | Layer 4 and Layer 7 load balancing with SSL termination and health checks |
| Monitoring and Alarms | Real-time metrics collection, dashboards, and automated alarm notifications |
| Cloud Guard | Automated security monitoring and threat detection across OCI resources |
| Vault and Key Management | Hardware security module-backed encryption key management and secret storage |
| Disaster Recovery | Automated disaster recovery orchestration for complex multi-tier applications |
| Generative AI | Large language model hosting and inference with customizable foundation models |
| Data Science | Managed Jupyter notebooks and ML model lifecycle management platform |

## Use Cases

| Name | Description |
|------|-------------|
| Cloud Migration | Migrate on-premises workloads to OCI with tools for assessment, planning, and execution |
| High Performance Computing | Run HPC workloads with bare metal instances, RDMA networking, and cluster networking |
| Data Warehousing | Build scalable data warehouses with Autonomous Database and integrated analytics |
| DevOps and CI/CD | Automate build, test, and deployment pipelines with OCI DevOps and Container Engine |
| Disaster Recovery | Implement business continuity with cross-region replication and automated failover |
| AI and Machine Learning | Train and deploy ML models using GPU instances, Data Science, and Generative AI services |
| Hybrid Cloud | Extend on-premises infrastructure with Cloud@Customer and dedicated regions |
| SaaS Extension | Extend Oracle SaaS applications with custom APIs and integrations on OCI |
| IoT and Edge Computing | Process IoT data at scale with streaming, functions, and edge infrastructure |
| Multi-Cloud Networking | Connect OCI with AWS, Azure, and Google Cloud using FastConnect and partnerships |

## Integrations

| Name | Description |
|------|-------------|
| Terraform | Infrastructure as Code provisioning with the OCI Terraform Provider |
| Ansible | Configuration management and automation with OCI Ansible Collection |
| Grafana | Metrics visualization with the OCI Grafana Plugin for Monitoring data |
| Kubernetes | Container orchestration with managed OKE clusters and Helm chart support |
| Visual Studio | IDE integration with OCI Tools for Visual Studio |
| VS Code | IDE integration with OCI Toolkit for Visual Studio Code |
| Eclipse | IDE integration with OCI Toolkit for Eclipse |
| GitHub Actions | CI/CD automation with OCI GitHub Actions for deployment pipelines |
| Oracle Integration Cloud | Pre-built connectors for SaaS and on-premises application integration |
| Microsoft Azure | Oracle Database@Azure for running Oracle databases on Azure infrastructure |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Compute](openapi/oracle-cloud-compute-openapi.yaml)
- [Database](openapi/oracle-cloud-database-openapi.yaml)
- [Functions](openapi/oracle-cloud-functions-openapi.yaml)
- [Iam](openapi/oracle-cloud-iam-openapi.yaml)
- [Monitoring](openapi/oracle-cloud-monitoring-openapi.yaml)
- [Networking](openapi/oracle-cloud-networking-openapi.yaml)
- [Object Storage](openapi/oracle-cloud-object-storage-openapi.yaml)
- [Oke](openapi/oracle-cloud-oke-openapi.yaml)

### JSON Schema

- [Compute Attach Volume Details](json-schema/compute-attach-volume-details-schema.json)
- [Compute Image](json-schema/compute-image-schema.json)
- [Compute Instance](json-schema/compute-instance-schema.json)
- [Compute Launch Instance Details](json-schema/compute-launch-instance-details-schema.json)
- [Compute Shape](json-schema/compute-shape-schema.json)
- [Compute Update Instance Details](json-schema/compute-update-instance-details-schema.json)
- [Compute Volume Attachment](json-schema/compute-volume-attachment-schema.json)
- [Database Autonomous Database](json-schema/database-autonomous-database-schema.json)
- [Database Autonomous Database Summary](json-schema/database-autonomous-database-summary-schema.json)
- [Database Create Autonomous Database Details](json-schema/database-create-autonomous-database-details-schema.json)
- [Database Db System](json-schema/database-db-system-schema.json)
- [Database Db System Summary](json-schema/database-db-system-summary-schema.json)
- [Database Update Autonomous Database Details](json-schema/database-update-autonomous-database-details-schema.json)
- [Functions Application](json-schema/functions-application-schema.json)
- [Functions Application Summary](json-schema/functions-application-summary-schema.json)
- [Functions Create Application Details](json-schema/functions-create-application-details-schema.json)
- [Functions Create Function Details](json-schema/functions-create-function-details-schema.json)
- [Functions Function](json-schema/functions-function-schema.json)
- [Functions Function Summary](json-schema/functions-function-summary-schema.json)
- [Iam Compartment](json-schema/iam-compartment-schema.json)
- [Iam Create Group Details](json-schema/iam-create-group-details-schema.json)
- [Iam Create Policy Details](json-schema/iam-create-policy-details-schema.json)
- [Iam Create User Details](json-schema/iam-create-user-details-schema.json)
- [Iam Group](json-schema/iam-group-schema.json)
- [Iam Policy](json-schema/iam-policy-schema.json)
- [Iam Update User Details](json-schema/iam-update-user-details-schema.json)
- [Iam User](json-schema/iam-user-schema.json)
- [Monitoring Alarm](json-schema/monitoring-alarm-schema.json)
- [Monitoring Alarm Summary](json-schema/monitoring-alarm-summary-schema.json)
- [Monitoring Create Alarm Details](json-schema/monitoring-create-alarm-details-schema.json)
- [Monitoring Metric Data](json-schema/monitoring-metric-data-schema.json)
- [Monitoring Metric](json-schema/monitoring-metric-schema.json)
- [Monitoring Summarize Metrics Data Details](json-schema/monitoring-summarize-metrics-data-details-schema.json)
- [Monitoring Update Alarm Details](json-schema/monitoring-update-alarm-details-schema.json)
- [Networking Create Internet Gateway Details](json-schema/networking-create-internet-gateway-details-schema.json)
- [Networking Create Subnet Details](json-schema/networking-create-subnet-details-schema.json)
- [Networking Create Vcn Details](json-schema/networking-create-vcn-details-schema.json)
- [Networking Internet Gateway](json-schema/networking-internet-gateway-schema.json)
- [Networking Route Table](json-schema/networking-route-table-schema.json)
- [Networking Security List](json-schema/networking-security-list-schema.json)
- [Networking Subnet](json-schema/networking-subnet-schema.json)
- [Networking Update Vcn Details](json-schema/networking-update-vcn-details-schema.json)
- [Networking Vcn](json-schema/networking-vcn-schema.json)
- [Object Storage Bucket](json-schema/object-storage-bucket-schema.json)
- [Object Storage Bucket Summary](json-schema/object-storage-bucket-summary-schema.json)
- [Object Storage Create Bucket Details](json-schema/object-storage-create-bucket-details-schema.json)
- [Object Storage Create Preauthenticated Request Details](json-schema/object-storage-create-preauthenticated-request-details-schema.json)
- [Object Storage List Objects](json-schema/object-storage-list-objects-schema.json)
- [Object Storage Object Summary](json-schema/object-storage-object-summary-schema.json)
- [Object Storage Preauthenticated Request](json-schema/object-storage-preauthenticated-request-schema.json)
- [Object Storage Preauthenticated Request Summary](json-schema/object-storage-preauthenticated-request-summary-schema.json)
- [Object Storage Update Bucket Details](json-schema/object-storage-update-bucket-details-schema.json)
- [Oke Cluster](json-schema/oke-cluster-schema.json)
- [Oke Cluster Summary](json-schema/oke-cluster-summary-schema.json)
- [Oke Create Cluster Details](json-schema/oke-create-cluster-details-schema.json)
- [Oke Create Node Pool Details](json-schema/oke-create-node-pool-details-schema.json)
- [Oke Node Pool](json-schema/oke-node-pool-schema.json)
- [Oke Node Pool Summary](json-schema/oke-node-pool-summary-schema.json)
- [Oke Update Cluster Details](json-schema/oke-update-cluster-details-schema.json)

### JSON Structure

- [Compute Attach Volume Details](json-structure/compute-attach-volume-details-structure.json)
- [Compute Image](json-structure/compute-image-structure.json)
- [Compute Instance](json-structure/compute-instance-structure.json)
- [Compute Launch Instance Details](json-structure/compute-launch-instance-details-structure.json)
- [Compute Shape](json-structure/compute-shape-structure.json)
- [Compute Update Instance Details](json-structure/compute-update-instance-details-structure.json)
- [Compute Volume Attachment](json-structure/compute-volume-attachment-structure.json)
- [Database Autonomous Database](json-structure/database-autonomous-database-structure.json)
- [Database Autonomous Database Summary](json-structure/database-autonomous-database-summary-structure.json)
- [Database Create Autonomous Database Details](json-structure/database-create-autonomous-database-details-structure.json)
- [Database Db System](json-structure/database-db-system-structure.json)
- [Database Db System Summary](json-structure/database-db-system-summary-structure.json)
- [Database Update Autonomous Database Details](json-structure/database-update-autonomous-database-details-structure.json)
- [Functions Application](json-structure/functions-application-structure.json)
- [Functions Application Summary](json-structure/functions-application-summary-structure.json)
- [Functions Create Application Details](json-structure/functions-create-application-details-structure.json)
- [Functions Create Function Details](json-structure/functions-create-function-details-structure.json)
- [Functions Function](json-structure/functions-function-structure.json)
- [Functions Function Summary](json-structure/functions-function-summary-structure.json)
- [Iam Compartment](json-structure/iam-compartment-structure.json)
- [Iam Create Group Details](json-structure/iam-create-group-details-structure.json)
- [Iam Create Policy Details](json-structure/iam-create-policy-details-structure.json)
- [Iam Create User Details](json-structure/iam-create-user-details-structure.json)
- [Iam Group](json-structure/iam-group-structure.json)
- [Iam Policy](json-structure/iam-policy-structure.json)
- [Iam Update User Details](json-structure/iam-update-user-details-structure.json)
- [Iam User](json-structure/iam-user-structure.json)
- [Monitoring Alarm](json-structure/monitoring-alarm-structure.json)
- [Monitoring Alarm Summary](json-structure/monitoring-alarm-summary-structure.json)
- [Monitoring Create Alarm Details](json-structure/monitoring-create-alarm-details-structure.json)
- [Monitoring Metric Data](json-structure/monitoring-metric-data-structure.json)
- [Monitoring Metric](json-structure/monitoring-metric-structure.json)
- [Monitoring Summarize Metrics Data Details](json-structure/monitoring-summarize-metrics-data-details-structure.json)
- [Monitoring Update Alarm Details](json-structure/monitoring-update-alarm-details-structure.json)
- [Networking Create Internet Gateway Details](json-structure/networking-create-internet-gateway-details-structure.json)
- [Networking Create Subnet Details](json-structure/networking-create-subnet-details-structure.json)
- [Networking Create Vcn Details](json-structure/networking-create-vcn-details-structure.json)
- [Networking Internet Gateway](json-structure/networking-internet-gateway-structure.json)
- [Networking Route Table](json-structure/networking-route-table-structure.json)
- [Networking Security List](json-structure/networking-security-list-structure.json)
- [Networking Subnet](json-structure/networking-subnet-structure.json)
- [Networking Update Vcn Details](json-structure/networking-update-vcn-details-structure.json)
- [Networking Vcn](json-structure/networking-vcn-structure.json)
- [Object Storage Bucket](json-structure/object-storage-bucket-structure.json)
- [Object Storage Bucket Summary](json-structure/object-storage-bucket-summary-structure.json)
- [Object Storage Create Bucket Details](json-structure/object-storage-create-bucket-details-structure.json)
- [Object Storage Create Preauthenticated Request Details](json-structure/object-storage-create-preauthenticated-request-details-structure.json)
- [Object Storage List Objects](json-structure/object-storage-list-objects-structure.json)
- [Object Storage Object Summary](json-structure/object-storage-object-summary-structure.json)
- [Object Storage Preauthenticated Request](json-structure/object-storage-preauthenticated-request-structure.json)
- [Object Storage Preauthenticated Request Summary](json-structure/object-storage-preauthenticated-request-summary-structure.json)
- [Object Storage Update Bucket Details](json-structure/object-storage-update-bucket-details-structure.json)
- [Oke Cluster](json-structure/oke-cluster-structure.json)
- [Oke Cluster Summary](json-structure/oke-cluster-summary-structure.json)
- [Oke Create Cluster Details](json-structure/oke-create-cluster-details-structure.json)
- [Oke Create Node Pool Details](json-structure/oke-create-node-pool-details-structure.json)
- [Oke Node Pool](json-structure/oke-node-pool-structure.json)
- [Oke Node Pool Summary](json-structure/oke-node-pool-summary-structure.json)
- [Oke Update Cluster Details](json-structure/oke-update-cluster-details-structure.json)

### JSON-LD

- [Compute Attach Context](json-ld/oracle-cloud-compute-attach-context.jsonld)
- [Compute Context](json-ld/oracle-cloud-compute-context.jsonld)
- [Compute Launch Context](json-ld/oracle-cloud-compute-launch-context.jsonld)
- [Compute Update Context](json-ld/oracle-cloud-compute-update-context.jsonld)
- [Compute Volume Context](json-ld/oracle-cloud-compute-volume-context.jsonld)
- [Database Autonomous Context](json-ld/oracle-cloud-database-autonomous-context.jsonld)
- [Database Create Context](json-ld/oracle-cloud-database-create-context.jsonld)
- [Database Db Context](json-ld/oracle-cloud-database-db-context.jsonld)
- [Database Update Context](json-ld/oracle-cloud-database-update-context.jsonld)
- [Functions Application Context](json-ld/oracle-cloud-functions-application-context.jsonld)
- [Functions Context](json-ld/oracle-cloud-functions-context.jsonld)
- [Functions Create Context](json-ld/oracle-cloud-functions-create-context.jsonld)
- [Functions Function Context](json-ld/oracle-cloud-functions-function-context.jsonld)
- [Iam Context](json-ld/oracle-cloud-iam-context.jsonld)
- [Iam Create Context](json-ld/oracle-cloud-iam-create-context.jsonld)
- [Iam Update Context](json-ld/oracle-cloud-iam-update-context.jsonld)
- [Monitoring Alarm Context](json-ld/oracle-cloud-monitoring-alarm-context.jsonld)
- [Monitoring Context](json-ld/oracle-cloud-monitoring-context.jsonld)
- [Monitoring Create Context](json-ld/oracle-cloud-monitoring-create-context.jsonld)
- [Monitoring Metric Context](json-ld/oracle-cloud-monitoring-metric-context.jsonld)
- [Monitoring Summarize Context](json-ld/oracle-cloud-monitoring-summarize-context.jsonld)
- [Monitoring Update Context](json-ld/oracle-cloud-monitoring-update-context.jsonld)
- [Networking Context](json-ld/oracle-cloud-networking-context.jsonld)
- [Networking Create Context](json-ld/oracle-cloud-networking-create-context.jsonld)
- [Networking Internet Context](json-ld/oracle-cloud-networking-internet-context.jsonld)
- [Networking Route Context](json-ld/oracle-cloud-networking-route-context.jsonld)
- [Networking Security Context](json-ld/oracle-cloud-networking-security-context.jsonld)
- [Networking Update Context](json-ld/oracle-cloud-networking-update-context.jsonld)
- [Object Storage Context](json-ld/oracle-cloud-object-storage-context.jsonld)
- [Oke Cluster Context](json-ld/oracle-cloud-oke-cluster-context.jsonld)
- [Oke Context](json-ld/oracle-cloud-oke-context.jsonld)
- [Oke Create Context](json-ld/oracle-cloud-oke-create-context.jsonld)
- [Oke Node Context](json-ld/oracle-cloud-oke-node-context.jsonld)
- [Oke Update Context](json-ld/oracle-cloud-oke-update-context.jsonld)

### Examples

- [Compute Attach Volume Details](examples/compute-attach-volume-details-example.json)
- [Compute Image](examples/compute-image-example.json)
- [Compute Instance](examples/compute-instance-example.json)
- [Compute Launch Instance Details](examples/compute-launch-instance-details-example.json)
- [Compute Shape](examples/compute-shape-example.json)
- [Compute Update Instance Details](examples/compute-update-instance-details-example.json)
- [Compute Volume Attachment](examples/compute-volume-attachment-example.json)
- [Database Autonomous Database](examples/database-autonomous-database-example.json)
- [Database Autonomous Database Summary](examples/database-autonomous-database-summary-example.json)
- [Database Create Autonomous Database Details](examples/database-create-autonomous-database-details-example.json)
- [Database Db System](examples/database-db-system-example.json)
- [Database Db System Summary](examples/database-db-system-summary-example.json)
- [Database Update Autonomous Database Details](examples/database-update-autonomous-database-details-example.json)
- [Functions Application](examples/functions-application-example.json)
- [Functions Application Summary](examples/functions-application-summary-example.json)
- [Functions Create Application Details](examples/functions-create-application-details-example.json)
- [Functions Create Function Details](examples/functions-create-function-details-example.json)
- [Functions Function](examples/functions-function-example.json)
- [Functions Function Summary](examples/functions-function-summary-example.json)
- [Iam Compartment](examples/iam-compartment-example.json)
- [Iam Create Group Details](examples/iam-create-group-details-example.json)
- [Iam Create Policy Details](examples/iam-create-policy-details-example.json)
- [Iam Create User Details](examples/iam-create-user-details-example.json)
- [Iam Group](examples/iam-group-example.json)
- [Iam Policy](examples/iam-policy-example.json)
- [Iam Update User Details](examples/iam-update-user-details-example.json)
- [Iam User](examples/iam-user-example.json)
- [Monitoring Alarm](examples/monitoring-alarm-example.json)
- [Monitoring Alarm Summary](examples/monitoring-alarm-summary-example.json)
- [Monitoring Create Alarm Details](examples/monitoring-create-alarm-details-example.json)
- [Monitoring Metric Data](examples/monitoring-metric-data-example.json)
- [Monitoring Metric](examples/monitoring-metric-example.json)
- [Monitoring Summarize Metrics Data Details](examples/monitoring-summarize-metrics-data-details-example.json)
- [Monitoring Update Alarm Details](examples/monitoring-update-alarm-details-example.json)
- [Networking Create Internet Gateway Details](examples/networking-create-internet-gateway-details-example.json)
- [Networking Create Subnet Details](examples/networking-create-subnet-details-example.json)
- [Networking Create Vcn Details](examples/networking-create-vcn-details-example.json)
- [Networking Internet Gateway](examples/networking-internet-gateway-example.json)
- [Networking Route Table](examples/networking-route-table-example.json)
- [Networking Security List](examples/networking-security-list-example.json)
- [Networking Subnet](examples/networking-subnet-example.json)
- [Networking Update Vcn Details](examples/networking-update-vcn-details-example.json)
- [Networking Vcn](examples/networking-vcn-example.json)
- [Object Storage Bucket](examples/object-storage-bucket-example.json)
- [Object Storage Bucket Summary](examples/object-storage-bucket-summary-example.json)
- [Object Storage Create Bucket Details](examples/object-storage-create-bucket-details-example.json)
- [Object Storage Create Preauthenticated Request Details](examples/object-storage-create-preauthenticated-request-details-example.json)
- [Object Storage List Objects](examples/object-storage-list-objects-example.json)
- [Object Storage Object Summary](examples/object-storage-object-summary-example.json)
- [Object Storage Preauthenticated Request](examples/object-storage-preauthenticated-request-example.json)
- [Object Storage Preauthenticated Request Summary](examples/object-storage-preauthenticated-request-summary-example.json)
- [Object Storage Update Bucket Details](examples/object-storage-update-bucket-details-example.json)
- [Oke Cluster](examples/oke-cluster-example.json)
- [Oke Cluster Summary](examples/oke-cluster-summary-example.json)
- [Oke Create Cluster Details](examples/oke-create-cluster-details-example.json)
- [Oke Create Node Pool Details](examples/oke-create-node-pool-details-example.json)
- [Oke Node Pool](examples/oke-node-pool-example.json)
- [Oke Node Pool Summary](examples/oke-node-pool-summary-example.json)
- [Oke Update Cluster Details](examples/oke-update-cluster-details-example.json)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Compute](capabilities/shared/compute.yaml)
- [Database](capabilities/shared/database.yaml)
- [Functions](capabilities/shared/functions.yaml)
- [Iam](capabilities/shared/iam.yaml)
- [Monitoring](capabilities/shared/monitoring.yaml)
- [Networking](capabilities/shared/networking.yaml)
- [Object Storage](capabilities/shared/object-storage.yaml)
- [Oke](capabilities/shared/oke.yaml)

### Workflow Capabilities

| Workflow | File |
|----------|------|
| [Cloud Native Development](capabilities/cloud-native-development.yaml) | cloud-native-development.yaml |
| [Data Platform](capabilities/data-platform.yaml) | data-platform.yaml |
| [Infrastructure Management](capabilities/infrastructure-management.yaml) | infrastructure-management.yaml |
| [Security And Compliance](capabilities/security-and-compliance.yaml) | security-and-compliance.yaml |

## Vocabulary

- [Oracle Cloud Vocabulary](vocabulary/oracle-cloud-vocabulary.yaml)

## Rules

- [Oracle Cloud Spectral Rules](rules/oracle-cloud-spectral-rules.yml)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
