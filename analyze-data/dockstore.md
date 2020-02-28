# Dockstore

[Dockstore](https://dockstore.org/) is a repositiory for Dockerized bioinformatics workflows. \(Not familar with Docker? [We’ve got docs for that too.](https://docs.dockstore.org/en/develop/getting-started/getting-started-with-docker.html)\) The beauty of Dockerized workflows is that they come packaged with all of their requirements, meaning you spend less time searching the web for obscure installation errors and more time doing research. What makes Dockstore different from websites such as [Dockerhub](https://hub.docker.com/) is that Dockstore workflows can be exported to cloud platforms directly, making it great for those who may not have access to their own computational cluster. Plus, Dockstore is specifically for bioinformatics workflows, meaning you spend less time wading through packages which aren’t relevant to your needs.

There’s more than one cloud computing solution out there. Using the NHLBI BioData Catalyst platform, you can launch both WDL and CWL workflows. On WDL workflows, you will be using Terra. For more information on how Dockstore integration with Terra works, [see here](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/community-tools/dockstore-example). On CWL workflows, that same button will take you to Seven Bridges.

![launch with BDC button](https://github.com/aofarrel/tutorials/blob/master/launchwith-cropped.png?raw=true)

That’s not the only option you have, though. The buttons you see will depend on the language of the workflow.

#### CWL Workflows <a id="CWL-Workflows"></a>

* NHLBI BioData Catalyst
* [CGL powered by Seven Bridges](https://docs.cancergenomicscloud.org/docs/run-dockstore-apps-on-the-cgc)

#### WDL Workflows <a id="WDL-Workflows"></a>

* NHLBI BioData Catalyst
* [Terra](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/community_tools/dockstore-example)
* [DNAstack](https://docs.dockstore.org/en/develop/launch-with/dnastack-launch-with.html)
* [DNAnexus](https://docs.dockstore.org/en/develop/launch-with/dnanexus-launch-with.html)

In addition to WDL, CWL, and Nextflow workflows, Dockstore also hosts sample JSONs so you can see exactly how to run these workflows. Some of these JSONs even link directly to sample data so you can be assured that your setup, whatever that might be, is fully functional. Bear in mind that if you are running on Terra, sample JSONs that contain URLs that link to Google Storage Buckets will need them in gs:// or drs:// format.

Dockstore is searchable, and you can search by both workflow properties–language, author, whether or not has an associated checker workflow, etc. So, for instance, if you only wanted to work in Seven Bridges as that is the platform you are the most familiar with, you can [limit your search to CWL workflows](https://dockstore.org/search?descriptorType=CWL&searchMode=files). You can also search by [an organization’s projects](https://dockstore.org/organizations). In particular, we want to point out two projects we’re passionate about: BioData Catalyst and TOPMed.

BioData Catalyst is an NHLBI project to build upon existing bioinformatics tools so that they work together in a way benefiting researchers. You can find more information on [their hub on Dockstore](https://dockstore.org/organizations/bdcatalyst).

TOPMed provides whole genome data for researchers along with phenotypic data and other omnics, with a focus on heart, lung, blood, and sleep disorders. You can find their collection on Dockstore [right here](https://dockstore.org/organizations/topmed), containing tools such as the workflows they used when aligning this data. If you are looking for more information on how to access the data itself, [check out our documentation on Gen3](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/explore_data/gen3-discovering-data), which is where the controlled access data is hosted.

