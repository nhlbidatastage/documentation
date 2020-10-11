# Advanced Topics

### Conversion tools

If you want your workflow to be available to both WDL and CWL communities, you can use conversion tools to aid in the process. It is best practice to review if the conversion was correctly done. 

* [cwl2wdl](https://github.com/adamstruck/cwl2wdl)
* [Wdl2cwl](https://github.com/common-workflow-lab/wdl2cwl)

### Running workflows outside of the BioData Catalyst ecosystem:

If you are interested in using Docker on your High-Performance Compute cluster, you may find the [Singularity](https://docs.dockstore.org/en/develop/advanced-topics/docker-alternatives.html) tool helpful.

You can use the workflow runner [Toil](https://github.com/DataBiosphere/toil) for large parallelized CWL jobs in the AWS and/or Google clouds, locally, on Kubernetes, and/or high-performance computer clusters.  [Toil](https://github.com/DataBiosphere/toil) is built for researchers and should run any CWL 1.0 workflow from Dockstore at scale.  [Toil](https://github.com/DataBiosphere/toil) also has some experimental support for WDL.

