---
description: An introduction to terms used in this document
---

# BYOT Glossary

Each platform within BioData Catalyst may have slight variations on these definitions. You will find a more specific definition within the section of the BYOT document. Below, we highlight a few terms to introduce you to before you get started. 

* **App:**  1\) In Seven Bridges, an app is a general term to refer to both tools and workflows. 2\) App may also refer to persistent software that is integrated into a platform. ****
* **Container:** A standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another \(for example, Docker\).
* **Command:** In workflow writing, the command specifies the literal command line run \(akin to what you would run in the terminal\). 
* **Common Workflow Language \(CWL\):** Simple scripting language for describing computational workflows for performing sequential operations on data. CWL is a way to describe command-line tools and connect them together to create workflows. CWL is well suited for describing large-scale workflows in cluster, cloud, and high-performance computing environments where tasks are scheduled in parallel across many nodes.
* **Docker:** Software for running packaged, portable units of code, and dependencies that can be run in the same way across many computers. See also **Container**.
* **Dockerfile:** A text document that contains all the commands a user could call on the command line to assemble an image.
* **Dockstore:** An open platform developed by the Cancer Genome Collaboratory and used by the GA4GH for sharing Docker-based tools described with the Common Workflow Language \(CWL\), the Workflow Description Language \(WDL\), or Nextflow \(NFL\).
* **Image:**  In the context of containers and Docker, this refers to the resting state of the software. 
* **Instance:** Refers to a virtual server instance from a public or private cloud network.
* Task: In workflow writing, the term task encompasses all of the information necessary to execute a command, such as specifying input/output files and parameters. 
* **Tool:** In CWL, the term tool specifies a single command. This specification is not as discrete in other languages such as WDL.
* **Workflow Description Language \(WDL\):** Way to specify data processing workflows with a human-readable and writable syntax. Define complex analysis tasks, chain them together in workflows, and parallelize their execution.
* **Workflow:** A sequence of processes, usually computational in this context, through which a user may analyze data.
* **Workspace:** Areas to work on/with data within a platform. Examples: projects within Seven Bridges.
* **Wrapping:** The process of describing a command-line tool or custom script in Common Workflow Language \(CWL\) so that it can be easily run in multiple cloud environments, dynamically scale compute requirements based on inputs, and be inserted into distinct analysis pipelines.
* **Virtual Machine \(VM\):** An isolated computing environment with its own operating system. ****

**For other terms, you can reference the** [**BioData Catalyst glossary**](https://bdcatalyst.gitbook.io/biodata-catalyst-consortium-guidance/glossary/biodata-catalyst-consortium-glossary)**.**   


