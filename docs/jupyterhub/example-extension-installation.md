---
layout: default
title: Example Extension Installation
parent: Installing JupyterHub Extensions
grand_parent: JupyterHub
nav_order: 2
description: ""
permalink: /jupyterhub/extension-installation/example-extension-installation
---



# Example Extension Installation Using JupyterLab-NVDashboard and Ollama
<br />
This section will provide a step-by-step example for installing the extension, [jupyterlab-nvdashboard](https://github.com/rapidsai/jupyterlab-nvdashboard). Please save your work and [shut down your notebook server](/jupyterhub/faqs/stopnotebook) before following the example.

### Installing the Extension
1) Start a new notebook server with the following server options.
![New notebook server options](/images/jupyterhub/extension-installation/nvdasboard-start-server.png)

2) Open a new terminal and use the command below to install the jupyterlab-nvdashboard extension:
```bash
pip install --user jupyterlab-nvdashboard
```

3) Once you have restarted the notebook or refreshed the window, you should see the extension installed on the left sidebar. Click refresh on the "Installed" dropdown menu to see jupyterlab-nvdashboard there as well.

![Extension Listed in Sidebar](/images/jupyterhub/extension-installation/nvdashboard-extension-installed-sidebar.png)

Use the find command from before to see that it's installed in your home directory
```bash
find ~ -name "jupyterlab-nvdashboard"
```
<br />

### Testing Extension using Ollama
1) Click the “+” button at the top to open another tab, then open a new terminal.

![Open new tab](/images/jupyterhub/extension-installation/nvdasboard-new-tab.png)

2) Run the command:
```bash 
ollama serve
```
- This will start the Ollama process so it can run AI/LLM models within this notebook. Let it run in that terminal.

3) In a new tab, open another terminal and use the following command to pull the llama3 model:
```bash
ollama pull llama3
```

4) On the left sidebar, click the extension we just installed labeled **GPU Dashboards**. Select the option *GPU Memory* and make a note of the memory that has been used so far.

5) Now, use the command 
```bash
ollama run llama3
```
This command may take some time to run. Once the command finishes, you should be able to write some prompts for the llama3 model.

![Talk with llama3](/images/jupyterhub/extension-installation/nvdashboard-run-llama3.png)


When you get some responses back from the model, check the *GPU Memory Tab* again to see the increase in memory usage. You can also click on the *GPU Resources* option to see how it’s being used overtime.

![GPU Memory](/images/jupyterhub/extension-installation/nvdashboard-GPU-Memory.png)

![GPU Resources](/images/jupyterhub/extension-installation/nvdashboard-GPU-Resources.png)


### Cleaning Up
1) After you're done talking with the model, enter `/bye`.

2) Use the following commands in order to remove the llama3 model that we pulled and stop the Ollama process.

```bash
ollama stop llama3 && ollama rm llama3
```
and

```bash
pkill ollama
```

3) Uninstall the extension using the command below:

```bash
pip uninstall jupyterlab-nvdashboard -y
```

{: .note }
For any specific software questions related to an extension, please refer to the extension's official documentation.