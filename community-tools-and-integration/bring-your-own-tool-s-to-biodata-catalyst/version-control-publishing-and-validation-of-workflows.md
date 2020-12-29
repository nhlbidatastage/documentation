# Version Control, Publishing, and Validation of Workflows

Version control is vital in reproducibility since it helps track changes you or contributors make to your code and documentation. We suggest using GitHub to host your workflows in an open access repository so that the research community can benefit from your work, and your work can benefit from feedback by the research community. Dockstore, our repository of Docker-based workflows, syncs automatically with GitHub. Below, find steps for getting started with GitHub and Dockstore: 

* [Create a GitHub account](https://www.github.com/join)
* [A primer on GitHub](https://lab.github.com/githubtraining/introduction-to-github)
* If you haven’t already, [Create a Dockstore Account](https://docs.dockstore.org/en/develop/getting-started/register-on-dockstore.html?highlight=register) and link your account to external services including Github
* Upload your workflow to a GitHub repository
* [Register your tool on Dockstore](https://docs.dockstore.org/en/develop/getting-started/dockstore-tools.html)
* [Automatically sync updates between GitHub and Dockstore with GitHub Apps](https://docs.dockstore.org/en/develop/getting-started/github-apps/github-apps-landing-page.html)
* [Request a DOI for your Dockstore workflow](https://docs.dockstore.org/en/develop/advanced-topics/snapshot-and-doi.html?highlight=doi)

### Source Control Best Practices

We suggest you check out this article [_On best practices in the development of bioinformatics software_](https://www.frontiersin.org/articles/10.3389/fgene.2014.00199/full)\_\_

When structuring your GitHub repositories, we suggest that you create different repositories for each workflow you develop. Below are helpful examples of how researchers have set up workflow projects on GitHub:

* [GENESIS CWL project on Seven Bridges GitHub Repository](https://github.com/sevenbridges-openworkflows/uw-genesis-topmed-cwl)
* [GENESIS WDL project on Analysis Commons GitHub Repository](https://github.com/AnalysisCommons/genesis_wdl/)

### Documentation Best Practices

Documentation is essential to reproducibility. When releasing your work on Github and publishing workflows on Dockstore, it is essential that you provide a comprehensive README. We recommend that documentation associated with new workflows includes:

* The software used in the workflow
* Important assumptions 
* Inputs and outputs of the workflow; specifying required vs optional inputs
* A description of the analysis
* Contact information for the workflow maintainer
* Relevant links to external resources 

### Dockstore Best Practices

Dockstore has outlined a set of [best practices](https://docs.dockstore.org/en/develop/advanced-topics/best-practices/best-practices-dockstore.html) for publishing your work in the repository. 

