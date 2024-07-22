
---
title: "RadiantOne Automated Remediation"
description : "RadiantOne Automated Remediation"
---

# RadiantOne Automated Remediation

When Identity Analytics is deployed along with Identity Data Management it is possible to automatically push remediation actions to the source systems.

At the time of writing, this is possible to:

- Revoke an account
- Remove a group membership

Please consult the *Remediation Interface functionalities* section of the [User Access Review](../uar-guide/03-key-concepts) guide if you want more information about how to configure a remediation strategy.

One of the prerequisites for automated remediation to operate is that the data is loaded through **Identity Data Management**. Several connectors are provided OOB to load data from RadiantOne. When you use those connectors you have nothing to do, remediation will be automatically enabled of configured.

There is a special use case when you want to load data from RadiantOne with your own ETL configuration. In that case, you have to configure the collect line in your project and you have to explicitly configure the lineage in order to activate the remediation:

- **Repository custom9** attribute **must** contain the string value `iddm`
- **account custom38** attribute **must** contain the iddm `actualdn` of the entry
- **account custom39** attribute **must** contain the iddm `virtualdn` of the entry
- **group custom8** attribute **must** contain the iddm `actualdn` of the entry
- **group custom9** attribute **must** contain the iddm `virtualdn` of the entry
