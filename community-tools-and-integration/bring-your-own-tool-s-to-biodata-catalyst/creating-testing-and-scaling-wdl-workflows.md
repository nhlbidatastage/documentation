# Creating, testing, and scaling WDL workflows

In this section, the reader will learn how to use the Terra and Dockstore platforms for the creation of WDL workflows for analysis and sharing with the scientific community. Below we have compiled community and BioData Catalyst resources to help users get started learning WDL to create their own workflows.

### Helpful definitions of terms when working on Terra

**Workspace:** A dedicated space where you and collaborators can access and organize the same data and tools and run analyses together. They can include: data, notebooks, and workflows. They can be public or controlled access.

**Workflow:** Chains of connected tools to accomplish a full analysis. Tools are often connected in a specific way to enable maximum computational efficiency and are also constructed to accomplish a specific analysis goal. A workflow typically describes a full analysis \(e.g. variant discovery, differential expression, or multiple variant association tests\).

**Workflow Description Language \(WDL\)**: A community-driven standard for describing data analysis pipelines and is easily portable across different computing environments. It is the language currently used to run batch-processes in Terra, which uses Cromwell as an executor. Like other descriptor languages, it is paired with Docker containers and can execute pipelines written in any language \(bash, R, Python, etc.\). Below, we have compiled community and BioData Catalyst resources to help users get started learning WDL to create their own tools and workflows.  


### WDL Toolkit: All the tools you need to write and run WDLs

* **Syntax**:
  * [WDL 1.0 Specification](https://github.com/openwdl/wdl/blob/main/versions/1.0/SPEC.md)
  * [WDL Script Components](https://support.terra.bio/hc/en-us/sections/360007350012-Script-Components)
* **Authoring:** 
  * [SublimeText](https://www.sublimetext.com/) offers a nice balance between usability and editing features.
  * Syntax highlighters: Plugins that enable syntax highlighting \(i.e. coloring code elements based on their function\) for supported text editors. Syntax highlighting has been developed for [SublimeText and Visual Studio](https://github.com/broadinstitute/wdl-sublime-syntax-highlighter), [vim](https://github.com/broadinstitute/vim-wdl), and [IntelliJ](https://github.com/broadinstitute/winstanley#winstanley-an-intellij-plug-in-for-wdl).
* **Visualization**: [Pipeline Builder](http://pb.opensource.epam.com/) is a web-based tool that creates an interactive graphical representation of any workflow written in WDL; also includes WDL code generation functionality. 
* **Execution engine**: [Cromwell](https://support.terra.bio/hc/en-us/articles/360037487871-Execute-) is an execution engine co-developed with WDL; it can be used on multiple platforms through pluggable backends and offers sophisticated pipeline execution features. See the doc entry on [execution](https://support.terra.bio/hc/en-us/articles/360037487871) for quickstart instructions.
* **Validation & inputs**: [WOMTool](https://cromwell.readthedocs.io/en/stable/WOMtool/) is a Java command-line tool co-developed with WDL that performs utility functions, including syntax validation and generation of input JSON templates. See the doc entries on [validation](https://support.terra.bio/hc/en-us/articles/360037486851) and [inputs](https://support.terra.bio/hc/en-us/articles/360037120252) for quickstart instructions.
* **Running tools**:
  * [Terra](https://support.terra.bio/hc/en-us/sections/360008068731-BioData-Catalyst) is a cloud-based analysis platform for running workflows written in WDL via Cromwell on Google Cloud; it is open to the public and offers sophisticated data and workflow management features. In this BYOT document, we walk through all of the steps to run a workflow in Terra. 
  * [Dockstore’s Command Line Interface](https://dockstore.org/quick-start)
  * [Wdl\_runner](https://github.com/broadinstitute/wdl-runner) is a lightweight command-line workflow submission system that runs WDLs via Cromwell on Google Cloud.
  * [wdlRunR](https://github.com/seandavi/wdlRunR) is a Bioconductor package to manage WDL workflows from within R, developed by Sean Davis. See docs [here](https://seandavi.github.io/wdlRunR/).

### Learning Resources for writing WDL

Below are a few learning resource tutorials we have compiled from various sources:

* Open WDL’s [Learn WDL](https://github.com/openwdl/learn-wdl) offers a comprehensive set of exercises for users that are just learning WDL. 
* [Getting Started with WDL](https://docs.dockstore.org/en/develop/getting-started/getting-started-with-wdl.html) from Dockstore is an introductory guide. 
* These Dockstore [training exercises](https://github.com/dockstore/bcc2020-training) along with this accompanying [video](https://www.youtube.com/watch?v=shMr_Bd01Ko&t=3226s) provide more complex examples using common bioinformatics tools.
* Once you are more familiar with writing workflows, we suggest you continue with [WDL Best Practices](https://docs.dockstore.org/en/develop/advanced-topics/best-practices/wdl-best-practices.html) from Dockstore.

### Writing your workflow locally using Dockstore’s Command Line Interface

You can start developing your WDL worfklow locally with Dockstore’s CLI and a small test dataset. This route allows you to debug syntax errors while avoiding cloud costs. Once your workflow is debugged, you can launch in a cloud environment to test for permissions errors and scaling issues. The Dockstore CLI automatically installs the Cromwell execution engine for running WDL workflows locally. 

Instructions: 

* [Create a Dockstore Account](https://docs.dockstore.org/en/develop/getting-started/register-on-dockstore.html?highlight=register)
* [Install Dockstore’s CLI](https://dockstore.org/quick-start) locally
* [Install Docker](https://docs.docker.com/engine/install/ubuntu/) locally
* This [example WDL exercise using Dockstore’s CLI](https://docs.dockstore.org/en/develop/getting-started/getting-started-with-wdl.html) steps through creating a basic WDL workflow locally and pushing the tool to GitHub, triggering an automated build on Quay.io. 

### Building and releasing your workflow

In order to transition your workflow from local development to Terra, a typical approach is to make the workflow available in a GitHub repository and then build. Quay.io integrates with Dockstore and GitHub by automatically building upon GitHub pushes. The Quay.io build can then be registered on Dockstore. You can follow the steps for linking your Dockstore account to external services like Quay.io in this [document](https://docs.dockstore.org/en/develop/getting-started/register-on-dockstore.html). 

 You can find more information about this process in section _Version Control, Publishing, and Validation of Workflows_ below.   


### Testing and using your workflow in the cloud with Terra

  
****Now that you have a workflow ready for running in a cloud environment, you can port your workflow into Terra in two ways. First, if you are already using Dockstore and GitHub for version control, you can navigate to your Dockstore WDL workflow and use the "Launch with NHLBI BioData Catalyst" button. This article [**Importing a Dockstore workflow into Terra**](https://support.terra.bio/hc/en-us/articles/360038137292) ****provides instructions for selecting a workflow in Dockstore then conveniently importing that workflow into Terra

![](https://lh6.googleusercontent.com/CIp0M8UXZnu0jmK3NpG1p2C5MygZePnbKu1wVHeSvg5bXAAMZNZy_85Xp7je2uBFAeHIJcPChDD2pcE8ydCGJbaqyMGr4zG7cj2aeikXEg0vHC5uTzvh-xh1QJotweMLpliW2l44)

                       **Figure 1**. Dockstore’s “Launch with BioData Catalyst” button.   


If you haven’t published your workflow to Dockstore, you can also [upload a workflow directly into Terra](https://support.terra.bio/hc/en-us/articles/360031366091-Create-edit-and-share-a-new-workflow) using the Broad Methods Repository. The Broad Methods Repository can easily be found in the “Add workflows” section of your Terra workspace. Similar to Dockstore, this repository hosts many WDL workflows that have been created by the Terra community. These workflows are only public once a user has signed into Terra.   


![](https://lh5.googleusercontent.com/MFBy23Tn7HeHRk9lPJb8ruojxpyRndEYxu9XXGkiEGIYKJKKueqjaJNuuIprhB0FmH4w0g4QYpSBV_-l6uqjtT_OlL5VW9hWlwTUWtxFyURWmwNGfjynZUZVltjRESNEP3rwjfE3)

**Figure 2**. In Terra workspaces, when you are in the "Workflows" tab you can “Find Additional Workflows” from Dockstore and the Broad Methods Repository.  


Once your workflow is in Terra, you may want to check out some of the learning resources below for configuring, troubleshooting, and optimizing your workflow. There are likely additional configuring and troubleshooting steps needed for getting your workflow up and running on larger datasets hosted in the cloud.

* [Terra’s Quickstart Workflows Workspace](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/fc-product-demo/Terra-Workflows-Quickstart)
* [Configure a workflow to process your data](https://support.terra.bio/hc/en-us/articles/360026521831-Configure-a-workflow-to-process-your-data)
* [Default runtime attributes for workflows](https://support.terra.bio/hc/en-us/articles/360046944671-Default-runtime-attributes-for-workflow-submissions)
* [Troubleshooting workflows: tips & tricks](https://support.terra.bio/hc/en-us/articles/360027920592)
* [Troubleshooting workflows: Fail for an unknown reason](https://support.terra.bio/hc/en-us/articles/360036927631)
* [Retrieve the time and cost of workflow jobs](https://support.terra.bio/hc/en-us/articles/360037862771-How-do-I-retrieve-the-time-and-cost-of-my-workflow-)

### Optimizing workflows on Terra

Terra also has several tips for reducing costs in order to promote the efficiency of a workflow. These approaches include deleting intermediate files and returning only final output to limit storage costs. Virtual machines can be configured with certain settings with reduced costs, such as using preemptible machines that trade-off reduced costs for the potential interruption. Cost optimizations are described at the following links:

* [Controlling cloud costs](https://support.terra.bio/hc/en-us/articles/360029772212-Controlling-Cloud-costs-sample-use-cases)
* [Enabling call-caching & deleting intermediate files](https://support.terra.bio/hc/en-us/articles/360039681632-Saving-storage-costs-by-deleting-Intermediate-files)
* [Experimental Jupyter Notebook for estimating costs of workflows run in Terra](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/Workflow%20Cost%20Estimator.ipynb)

Once your workflow is working as expected, we ask that you publish your work to share with the research community. You can find resources for how to publish your work on GitHub and Dockstore in the section below titled _Version Control, Publishing, and Validation of Workflows_.   


