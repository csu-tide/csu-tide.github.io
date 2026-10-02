---
layout: default
title: Usage Guidelines Overview
parent: Usage Guidelines
nav_order: 10
has_children: false
description: ""
permalink: /usage-guidelines/
---

# Usage Guidelines

## Data Storage
All users start with **75 GB of storage** within the CSU TIDE JupyterHub ([see campus-specific information otherwise](/jupyterhub/gettingaccess#campus-specific-access)). Users are responsible for managing the storage they've been allocated including deletion of large, unused, and/or temporary files *(e.g. ML model checkpoints, old git repos, virtual environments)*.

**If users require more storage** than the default amount, please check out the [Storage Services](/storage-services/) section.

{: .note }
**Disclaimer**: TIDE currently has no storage that is suitable for HIPAA, PID, FISMA, FERPA, CSU Protected Level-1, or protected data of any kind. Users are not permitted to store such data on TIDE machines.

## Signing In to the NRP
**All new users** must sign in to the National Research Platform (NRP) and accept the [Acceptable Use Policy (AUP)](https://docs.nrp.ai/assets/NRP-AUP.pdf){:target="_blank"} before they can use the TIDE cluster:

1. Go to [nrp.ai](https://nrp.ai){:target="_blank"} to sign in to the NRP.
1. Click **Login** in the top-right corner.
1. Search for **San Diego State University** in the dropdown list.
    - **Note:** Do *not* select ORCID.
1. Authenticate with your SDSUid and multi-factor authentication, exactly as you normally would.

{: .note }
The first time you sign in, you will be asked to read and accept the NRP Acceptable Use Policy (AUP).

## Grant Acknowledgements
In addition to the usage guidelines above, **all users who publish work that used TIDE resources** must acknowledge the NRP and TIDE. Please include the following statements in the acknowledgements section of your publication:

> This work used resources available through the National Research Platform (NRP) at the University of California, San Diego. NRP has been developed, and is supported in part, by funding from National Science Foundation, from awards 1730158, 1540112, 1541349, 1826967, 2112167, 2100237, and 2120019, as well as additional funding from community partners.

> This work used resources provided through TIDE, which is supported by National Science Foundation award 2346701.

## Citations
Please also cite the following papers describing the NRP and TIDE infrastructure:

- Derek Weitzel, Ashton Graves, Sam Albin, Huijun Zhu, Frank Würthwein, Mahidhar Tatineni, Dmitry Mishin, John Graham, Elham E. Khoda, Mohammad Firas Sada, Larry Smarr, and Thomas DeFanti. 2025. *The National Research Platform: Stretched, Multi-Tenant, Scientific Kubernetes Cluster.* In *Practice and Experience in Advanced Research Computing 2025 (PEARC ’25)*. Association for Computing Machinery. [https://doi.org/10.1145/3708035.3736060](https://doi.org/10.1145/3708035.3736060){:target="_blank"}

- Michael Farley, Kyle Krick, and Henry Li. 2026. *TIDE: Regional GPU Cyberinfrastructure Integrated into the National Research Platform.* In *Practice and Experience in Advanced Research Computing 2026 (PEARC ’26)*. Association for Computing Machinery. [https://doi.org/10.1145/3785462.3815851](https://doi.org/10.1145/3785462.3815851){:target="_blank"}


BibTeX entries:

```
@inproceedings{10.1145/3708035.3736060,
author = {Weitzel, Derek and Graves, Ashton and Albin, Sam and Zhu, Huijun and Wuerthwein, Frank and Tatineni, Mahidhar and Mishin, Dmitry and Khoda, Elham and Sada, Mohammad and Smarr, Larry and DeFanti, Thomas and Graham, John},
title = {The National Research Platform: Stretched, Multi-Tenant, Scientific Kubernetes Cluster},
year = {2025},
isbn = {9798400713989},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3708035.3736060},
doi = {10.1145/3708035.3736060},
abstract = {The National Research Platform (NRP) represents a distributed, multi-tenant Kubernetes-based cyberinfrastructure designed to facilitate collaborative scientific computing. Spanning over 75 locations in the U.S. and internationally, the NRP uniquely integrates varied computational resources, ranging from single nodes to extensive GPU and CPU clusters, to support diverse research workloads including advanced AI and machine learning tasks. It emphasizes flexibility through user-friendly interfaces such as JupyterHub and low level control of resources through direct Kubernetes interaction. Critical operational insights are discussed, including security enhancements using Kubernetes-integrated threat detection, extensive monitoring, and comprehensive accounting systems. This paper highlights the NRP's growing importance and scalability in addressing the increasing demands for distributed scientific computational resources.},
booktitle = {Practice and Experience in Advanced Research Computing 2025: The Power of Collaboration},
articleno = {69},
numpages = {5},
keywords = {Distributed Computing, Kubernetes, High Throughput Computing, Artificial Intelligence},
location = {},
series = {PEARC '25}
}
```

```
@inproceedings{10.1145/3785462.3815851,
author = {Farley, Michael and Krick, Kyle and Li, Henry},
title = {TIDE: Regional GPU Cyberinfrastructure Integrated into the National Research Platform},
year = {2026},
isbn = {9798400723773},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3785462.3815851},
doi = {10.1145/3785462.3815851},
abstract = {The Technology Infrastructure for Data Exploration (TIDE) is a National Science Foundation (NSF) funded (#2346701) project that addresses the California State University (CSU) system's critical need for access to graphical processing units (GPUs) for research computing and can be a blueprint for regional computing efforts seeking to democratize access to GPUs for advanced research. TIDE established a shared, regional high-performance computing resource for advancing research in data intensive fields like artificial intelligence (AI) and machine learning (ML). To complement and to enable successful access to the infrastructure, TIDE funding also included a distributed support model including governance and direct user support.},
booktitle = {Proceedings of the Practice and Experience in Advanced Research Computing 2026: Resilient Roots + Empowered Communities},
articleno = {48},
numpages = {4},
keywords = {GPU cyberinfrastructure, High-performance computing, Research computing, Resource federation},
location = {},
series = {PEARC '26}
}
```