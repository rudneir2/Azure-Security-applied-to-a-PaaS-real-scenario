# Azure Security applied to a PaaS (real) scenario

## Intro

Security may be applied to any IT environment. Options are many!! It all dependes on the environment, if it is on-premises, on the cloud or a hybrid environment (on-premises + cloud).
Also, it will depend on the type of technologies and cloud provider that is part of that IT environment. It could even be a multi-cloud environment + on-premises, in any combination.

Microsoft Azure and many of its Security solutions support hybrid and multi-cloud environment. However, to simplify this Security scenario applied to a very common PaaS environment, we will consider an environment running on an Azure public cloud.

## The environment (based on a real company IT environment)

picture 1

This environment runs as its core an **AKS (Azure Kubernetes Services)** running many workloads, including Web Server and Applications, connected on a diversity of others services that compose the entire Company solution, including:

- **Azure Storage** (supporting the Web Servers)
- **Azure SQL Database** (MS SQL PaaS)
- **Redis cache** supporting the Azure SQL Database for a better performance
- **Service bus** connecting AKS applications to the Database
- **Cosmos DB**, a non-SQL database supporting other applications

For some professionals that are focused on the IT infrastructure or Applications side, sometimes **Security** and all options available to have a more Secure environment can go unnoticed!

## A Security perspective (same environment)

Now, let's take a look at in the same environment, but with a Security perspective.

picture 2
  
