# Azure Security applied to a PaaS (real) scenario

## Intro

Security may be applied to any IT environment. Options are many!! It all dependes on the environment, if it is on-premises, on the cloud or a hybrid environment (on-premises + cloud).
Also, it will depend on the type of technologies and cloud provider that is part of that IT environment. It could even be a multi-cloud environment + on-premises, in any combination.

Microsoft Azure and many of its Security solutions support hybrid and multi-cloud environment. However, to simplify this Security scenario applied to a very common PaaS environment, we will consider an environment running on an Azure public cloud.

## The environment (based on a real company IT environment)

![image](https://github.com/rudneir2/Azure-Security-applied-to-a-PaaS-real-scenario/assets/97529152/2a4245a5-4071-4b39-81aa-4157850fe689)

This environment runs as its core an **AKS (Azure Kubernetes Services)** running many workloads, including Web Server and Applications, connected on a diversity of others services that compose the entire Company solution, including:

- **Azure Storage** (supporting the Web Servers)
- **Azure SQL Database** (MS SQL PaaS)
- **Redis cache** supporting the Azure SQL Database for a better performance
- **Service bus** connecting AKS applications to the Database
- **Cosmos DB**, a non-SQL database supporting other applications

For some professionals that are focused on the IT infrastructure or Applications side, sometimes **Security** and all options available to have a more Secure environment can go unnoticed!

## A Security perspective (same environment)

Now, let's take a look at in a nutshell, the same environment above, but with a Security perspective.

![image](https://github.com/rudneir2/Azure-Security-applied-to-a-PaaS-real-scenario/assets/97529152/24885edc-8d73-4fd8-be96-c89099c431cd)
  
- In the highlighted area **number 1** we can see different (and possible) attackers, external and internal. We can still include anonymous attackers that can be anywhere.

- in the highlighted area **number 2** we have one of the most important component of an IT environment, **the network**. AKS uses lot of Azure network components and topology.

- in the highlighted area **number 3** we have **Identity**, in this scenario, totally provided by **Entra ID**.

- in the highlighted area **number 4** we have additional **PaaS Security services** like:

    - **API Management**, adding protection to API services
    - **Azure Key Vault**, adding protection to keys, secrets and certificates
 
- in the highlighted area **number 5** there are many Security services available with Storage account, that could be applied to Blobs (object storage) or Files (File servers).
- in the highlighted area **number 6** we may apply different Security features to Data Base services.
- in the highlighted area **number 7** we have some others PaaS services like **Redis, Service Bus and Container Registry** that also may have different ways to get those services more secure.

Below, we will review in details all Security services that may be applied to that IT environment.

## Security in detail (in a visual way)

![image](https://github.com/rudneir2/Azure-Security-applied-to-a-PaaS-real-scenario/assets/97529152/db78cc03-5326-4983-8168-133ac1e849ec)
      
    - 
