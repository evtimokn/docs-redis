---
title: Provisioning Redis instances on demand
owner: London Services
---

Version 1.8 of PCF Redis introduces on-demand provisioning of Redis instances based on the [On-Demand Services SDK](http://docs.pivotal.io/on-demand-service-broker/). This enables an App Developer to create a Redis instance as needed from the CF CLI through the `cf create-service` command. The Operator configures the plan options available to the App Developers.

Prior to PCF Redis 1.8.0, Redis for PCF offers Dedicated-VM and Shared-VM plans. This means that an Operator needs to specify at install time how many dedicated VM Redis instances to create.

The improved flexibility in how and when instances are created allows for more efficient and seamless resource use for both Operator and App Developer.

## <a id="service"></a>On Demand Service Plan Descriptions

PCF Redis offers three on-demand plans as the p.redis service within the PCF Redis tile. Below is a description of each plan as it appears in the cf marketplace and its intended use case.

* **Small Cache Plan**- A Redis instance deployed to a dedicated VM, suggested to be configured with ~2GB of memory and >10GB of persistent disk.
* **Medium Cache Plan** - A Redis instance deployed to a dedicated VM, suggested to be configured with ~2GB of memory and >10GB of persistent disk.
* **Large Cache**- A Redis instance deployed to a dedicated VM, suggested to be configured with ~4GB of memory and >14GB of persistent disk.

For each service plan, the operator can configure the **Plan name**, **Plan description**, **Server VM type** and **Server Disk type**, or choose to disable the plan completely.

## Additional Redis Configurations

On top of memory and disk sizes, further properties can be configured per plan. Appropriate defaults have been pre-configured according to the memory/disk size of each plan.