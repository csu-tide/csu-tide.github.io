---
layout: default
title: Extension Installation
parent: JupyterHub
nav_order: 7
has_children: false
description: ""
permalink: /jupyterhub/extension-installation
---

# Extension Installation
This documentation will guide you through how to search for extensions, install and uninstall them. At the end there is an 

within the JupyterHub environment.

{: .note }
This guide uses placeholders such as `[extension-name]`. Replace them with the appropriate values unless otherwise specified.

## How to Search for Extensions in JupyterHub
On the left sidebar, open the extension menu by clicking the puzzle piece icon. Here is where you can search for new and existing extensions using the search bar above. 

![Extension Manager](/images/jupyterhub/extension-installation/nvdashboard-search-extensions.png)

Additionally, under the dropdown menu titled "Installed," you can see all the extensions present within your JupyterHub environment.

## How to Install Extensions on JupyterHub
1) Open a Terminal from within your notebook environment.

![Click Terminal](/images/jupyterhub/extension-installation/nvdashboard-click-terminal.png)

2) In your terminal, use the command below followed by the extension’s name:

```bash
pip install --user [extension-name]
```
This installs the extension into the **/home/jovyan/** directory, where it can persist, or not be erased when you restart your notebook.


### Checking that the Extension is Installed

After installing the extension, save your work and try one of the following:
- [Restarting your notebook](/jupyterhub/faqs/stopnotebook)
- Refreshing your window

The extension should appear on the left side bar. You can also see it under your current extensions list by clicking the refresh icon.

![Refresh Installed Extension List](/images/jupyterhub/extension-installation/nvdashboard-refresh-installed-extension-list.png)

Another way to check that the extension is installed properly is by running the following command:
```bash
find ~ -name "[extension-name]"
```
This command will search for the extension in your home directory /home/jovyan/, represented by the tilde (~). If you don't receive any output, then the extension isn't installed or isn't installed in your home directory. <br><br>


## How to Remove an Extension

To uninstall an extension that was installed on your PVC, i.e., in your home directory, use the following command:

```bash
pip uninstall [extension-name] -y
```

### Check that the Extension is Uninstalled
- [Restart your notebook server](/jupyterhub/faqs/stopnotebook) or refresh your window.
- To double check, run the find command below with the extension name within the double quotes:
```bash
find ~ -name "[extension-name]"
```


## Example Extension Installation Using JupyterLab-NVDashboard and Ollama
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

## Example: Testing Extension using Ollama
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

### What to Do If Extensions/Packages Don't Fully Uninstall

In some cases, a Python package or JupyterHub extension installed under a different Python version may not uninstall completely. If that happens, follow these steps to safely remove them from your home directory:

1) Locate all related files or directories
```bash
find ~ -name "[extension-name]*"
```

2) Review the output carefully
- Make sure that the listed items contain **only** the files and directories associated with the extension you want to remove.

3) Delete the package or extension files
```bash
find ~ -name "[extension/package-name]*" -exec rm -rf {} +
```

{: .warning }
This command will remove all matching files or directories. Please confirm the results of the first command before running the delete command.
