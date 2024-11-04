---
layout: default
title: Server Options
parent: Frequently Asked Questions
grand_parent: JupyterHub
nav_order: 2
has_children: false
description: ""
permalink: /jupyterhub/faqs/serveroptions
---

# Server Options Page
When starting a new notebook from the Server Options page, there are many options to consider. What do these options mean and how does one select them appropriately? <br>

{: .note }
**Disclaimer**: This information focuses on the CSU TIDE JupyterHub. Refer to campus-specific information in [Getting Access](/jupyterhub/gettingaccess) as appropriate.

![Server Options Page](/images/jupyterhub/faq-serveroptions1.png)

# GPUs, CPU Cores, and RAM
Let's explain what GPUs, CPU Cores, and RAM are and how they can be useful in the context of research and instruction. 

A **GPU (Graphical Processing Unit)** is a specialized processor designed to perform many simple calculations in parallel. Here are some contexts where requesting a GPU is advantageous (assuming code that is designed to run on GPUs):

- AI/ML *(e.g. training a neural network)*
- Scientific Computing *(e.g. weather modeling)*
- Data Science and Big Data Analytics *(e.g. linear regression)*
- Medical Imaging *(e.g. 3D reconstructions)*

A **CPU core** is one of many small, yet powerful workers within a **CPU (Central Processing Unit)** designed for diverse and complex processing tasks in a sequential manner. Here are some contexts where requesting 2+ CPU cores is advantageous:

- Genomics and Bioinformatics *(e.g. protein-protein interactions)*
- Numerical Simulations *(e.g. combinatorial optimization)*
- Parallel Programming *(e.g. multithreading)*

**RAM (Random Access Memory)** is the short-term memory of a computer. RAM is designed to store data and program instructions that are currently being used by the computer's CPU. Persistent forms of memory like hard drives and SSDs retain data even when the power is turned off, whereas RAM gets wiped. Here are some contexts where requesting 8+ GB of RAM is advantageous:

- AI/ML *(e.g. natural language processing)*
- Big Data Analytics *(e.g. data mining)*
- Geospatial Analysis and Remote Sensing *(e.g. land cover classification)*

### Images
When using JupyterHub, researchers can choose from a variety of pre-built images that contain different combinations of software packages and dependencies. But, what is an "image"?

A **(container) image** is like a "ready-to-go box" that contains everything needed to run a program, including software, tools, configurations. TIDE leverages these images to provide individual pre-built environments containing a suite of software packages for tasks like machine learning, genomics, and more.

The *Images* option in the Server Options page allows researchers to quickly spin up a customized computing environment without having to manually install and configure each software package themselves. This saves time and reduces the risk of configuration errors or conflicts between packages.
