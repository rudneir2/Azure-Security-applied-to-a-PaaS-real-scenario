# Azure Security applied to a PaaS (real) scenario

## Intro

Security may be applied to any IT environment. Options are many!! It all dependes on the environment, if it is on-premises, on the cloud or a hybrid environment (on-premises + cloud).
Also, it will depend on the type of technologies and cloud provider that is part of that IT environment. It could even be a multi-cloud environment + on-premises, in any combination.

Microsoft Azure and many of its Security solutions support hybrid and multi-cloud environment. However, to simplify this Security scenario applied to a very common PaaS environment, we will consider an environment running on an Azure public cloud.

## The environment (based on a real company IT environment)

![image](https://github.com/rudneir2/Azure-Security-applied-to-a-PaaS-real-scenario/assets/97529152/7d1fa72e-03c2-4afd-bc81-be8cb63dc07b)

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

  In the highlighted area:

- **number 1:** we can see different (and possible) attackers, external and internal. We can still include anonymous attackers that can be anywhere.

- **number 2:** we have one of the most important component of an IT environment, **the network**. AKS uses lot of Azure network components and topology.

- **number 3:** we have **Identity**, in this scenario, totally provided by **Entra ID**.

- **number 4:** we have additional **PaaS Security services** like:

    - **API Management**, adding protection to API services
    - **Azure Key Vault**, adding protection to keys, secrets and certificates
 
- **number 5:** there are many Security services available with **Storage account**, that could be applied to Blobs (object storage) or Files (File servers).
- **number 6:** we may apply different Security features to **Data Base** services.
- **number 7:** we have some others PaaS services like **Redis, Service Bus** and **Container Registry** that also may have different ways to get those services more secure.

Below, we will review in **details** all Security services that may be applied to that IT environment.

## Security in detail (in a visual way)

Below is a visual diagram to help you identify easily Security services that you may apply to that IT environment. Below the diagram is a list of Security you may apply to AKS.

![image](https://github.com/rudneir2/Azure-Security-applied-to-a-PaaS-real-scenario/assets/97529152/db78cc03-5326-4983-8168-133ac1e849ec)

### AKS Security checklist

**During provisioning**

1. automatic upgrade
2. authentication through Azure AD with RBAC
3. node pool OS disk encryption with customer managed key
4. enable private cluster
5. bring your own virtual network (with all your rules)
6. use MDC for recommendations / security alerts
7. use private image registry (azure container registry)
8. Azure policies for AKS (review it)
9. enable container insights (Prometheus, Grafana or Az Monitor insights) (review it)
10. enable Alerts for CPU/memory metrics
11. enable key vault (for CSI driver) 
 
**From AKS Security baseline (summarized)**

1. use MDC to track recommendations for AKS
2. virtual network segmentation
3. in-transit criptography (inside the AKS cluster)
   - use service mesh or CSI driver (cilium or istio)
4. azure private link (private endpoint)
5. AKS managed Azure AD integration
6. use a Managed Identity with AKS (aka workload identity)
7. use conditional access with Azure AD and AKS
8. use RBAC for Kubernetes authorization
9. enable Microsoft Defender for Containers
10. Kubernetes cluster should be accessible only over HTPPS
11. azure container registry should be enabled with AKS
12. vulnerability management for AKS
13. Backup AKS using Azure Backup (based on Velero)

See details below on Azure Security Baseline.
      
## References

- AKS Security baseline
  
https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/azure-kubernetes-service-aks-security-baseline
  
- Azure Storage Security baseline
  
https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/storage-security-baseline

- Azure SQL database Security baseline
  
https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/azure-sql-security-baseline

- Redis Cache Security baseline

https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/azure-cache-for-redis-security-baseline

- Cosmos DB Security baseline

https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/azure-cosmos-db-security-baseline

- Service Bus Security baseline

https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/service-bus-security-baseline
