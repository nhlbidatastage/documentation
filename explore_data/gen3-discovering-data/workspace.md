---
description: Workspace on the BioData Catalyst Gen3 platform
---

# Workspace

When navigating to Workspace, a user will be presented with multiple workspace options.

![Gen3 BioData Catalyst Workspace Page.](../../.gitbook/assets/workspaces.png)

The Gen3 platform offers two workspace environments: Jupyter Notebooks and R Studio. At present, we offer six workspaces:

#### Virtual machines \(VM\): 

* Small Jupyter Notebook VM
* Large Jupyter Notebook Power VM
* R Studio VM

#### Pre-made workflow workspaces: 

* Autoencoder Demo
* CIP Demo
* Tensorflow-Pytorch. 

To start a workspace, click the Launch button. You should see the following launch loading screen below.

![The launching screen.](../../.gitbook/assets/workspace_loading.png)

{% hint style="info" %}
Launching a VM can take up to five minutes depending upon the size and complexity of the workspace.
{% endhint %}

Once the VM is ready, the initial screen for the workspace will appear. For scripts and output that need to be saved when the workspace is terminated, please store those files in the `pd/` directory. 

![The initial workspace for Jupyter Notebooks.](../../.gitbook/assets/python_workspace.png)

![The initial workspace for R Studio.](../../.gitbook/assets/r_workspace.png)

This workspace will persist once the user has logged out of the Gen3 BioData Catalyst system. If the workspace is no longer being used, **please terminate the workspace** using the `Terminate Workspace` button found at the bottom of the window. Doing this will return the user to the Workspace page with all the workspace options. 

More information about Gen3 Workspace can be found [here](https://gen3.org/resources/user/analyze-data/).

