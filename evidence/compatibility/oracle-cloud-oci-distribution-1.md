<!-- fetched 2026-10-13 from https://docs.oracle.com/en-us/iaas/Content/Registry/Concepts/registryoverview.htm by sweep-shape-compat.py; text extracted from the provider's own page -->

Overview of Container Registry 
 Oracle Cloud Infrastructure Documentation 
 All Pages 
 Skip to main content 
 Overview of Container Registry
 Find out about Container Registry, an Oracle-managed registry that enables you to simplify your development to production workflow. 
 Oracle Cloud Infrastructure Registry (also known as Container Registry) is an Oracle-managed registry that enables you to simplify your development to production workflow. Container Registry makes it easy for you as a developer to store, share, and manage container images (such as Docker images). And the highly available and scalable architecture of Oracle Cloud Infrastructure ensures you can reliably deploy your applications. So you don't have to worry about operational issues, or scaling the underlying infrastructure.
 You can use Container Registry as a private Docker registry for internal use, pushing and pulling Docker images to and from the Container Registry using the Docker V2 API and the standard Docker command line interface (CLI). You can also use Container Registry as a public Docker registry, enabling any user with internet access and knowledge of the appropriate URL to pull images from public repositories in Container Registry.
 Container Registry is an Open Container Initiative -compliant registry. As a result, you can store container images (such as Docker images) that conform to Open Container Initiative specifications in Container Registry. You can also store manifest lists (sometimes known as multi-architecture images) to support multiple architectures (such as ARM and AMD64). And you can store Helm charts (for more information about the Helm feature that supports chart storage in Open Container Initiative-compliant registries, see Registries in the Helm documentation).
 Container Registry supports private access from other Oracle Cloud Infrastructure resources in a virtual cloud network (VCN) in the same region through a service gateway. Setting up and using a service gateway on a VCN lets resources (such as worker nodes in clusters managed by Kubernetes Engine) access Oracle Cloud Infrastructure services such as Container Registry without exposing them to the public internet. No internet gateway is required and resources can be in a private subnet and use only private IP addresses. For more information, see Access to Oracle Services: Service Gateway .
 Container Registry is integrated with IAM, which provides easy authentication with native Oracle Cloud Infrastructure identity.
 For an introductory tutorial, see Pushing an Image to Oracle Cloud Infrastructure Registry .
 Ways to Access Oracle Cloud Infrastructure
 You can access Oracle Cloud Infrastructure (OCI) by using the Console (a browser-based interface), REST API , or OCI CLI . Instructions for using the Console, API, and CLI are included in topics throughout this documentation. For a list of available SDKs, see Software Development Kits and Command Line Interface . 
 Note that Container Registry fully implements a Docker protocol that enables you to use the Docker Registry HTTP API (as well as the Oracle Cloud Infrastructure API) to manage images. See Preparing for Container Registry for the list of regional endpoints, and see the Docker documentation for information about using the Docker Registry HTTP API.
 Resource Identifiers
 Most types of Oracle Cloud Infrastructure resources have a unique, Oracle-assigned identifier called an Oracle Cloud ID (OCID). For information about the OCID format and other ways to identify your resources, see Resource Identifiers . 
 Authentication and Authorization
 Each service in Oracle Cloud Infrastructure integrates with IAM for authentication and authorization, for all interfaces (the Console, SDK or CLI, and REST API).
 An administrator in an organization needs to set up groups , compartments , and policies that control which users can access which services, which resources, and the type of access. For example, the policies control who can create new users, create and manage the cloud network, create instances, create buckets, download objects, and so on. For more information, see Managing Identity Domains . For specific details about writing policies for each of the different services, see Policy Reference . 
 If you're a regular user (not an administrator) who needs to use the Oracle Cloud Infrastructure resources that the company owns, contact an administrator to set up a user ID for you. The administrator can confirm which compartment or compartments you can use.
 Container Registry Capabilities and Limits
 In each region that is enabled for your tenancy, you can create up to 500 repositories in Oracle Cloud Infrastructure Registry consuming a maximum of 500 GB in total (if you need more storage, Contact Us ). Each repository can hold up to 100,000 images. See Limits by Service .
 You are charged for stored images, as shown in the Cloud Price List .
 Required IAM Service Policy
 To use Oracle Cloud Infrastructure, an administrator must be a member of a group granted security access in a policy by a tenancy administrator. This access is required whether you're using the Console or the REST API with an SDK, CLI, or other tool. If you get a message that you don't have permission or are unauthorized, verify with the tenancy administrator what type of access you have and which compartment your access works in.
 If you're new to policies, see Getting Started with Policies and Common Policies . 
 For more details about policies for Container Registry, see:
 Policies to Control Repository Access 
 Details for Container Registry 
 Overview of Container Registry 
 Ways to Access Oracle Cloud Infrastructure 
 Resource Identifiers 
 Authentication and Authorization 
 Container Registry Capabilities and Limits 
 Required IAM Service Policy 
 Copyright © 2026, Oracle and/or its affiliates. 
 About Oracle 
 Contact Us 
 Legal Notices 
 Terms of Use & Privacy 
 Document Conventions
