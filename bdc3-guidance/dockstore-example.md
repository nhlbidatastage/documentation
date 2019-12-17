# Dockstore integration with Terra

Dockstore integrates with the Terra platform, allowing you to launch
WDL-based workflows from Dockstore in Terra. This mini tutorial demonstrates 
what the Dockstore-Terra integration looks like from a user point of view.

## Exporting WDL workflows into Terra

When browsing WDL workflows from within Dockstore, you will see a
"Launch with Terra" button on the right. The currently selected version
of the workflow will be exported.

![Export current WDL workflow, launch with Terra button](../.gitbook/assets/terra_from_dockstore1.png "Export current WDL workflow, launch with Terra button")

*Figure 1: WDL workflow*

If not logged into Terra, you will be prompted to login. Otherwise, or
after login, you will be presented with the following screen.

![Terra import from Dockstore prompt](../.gitbook/assets/terra_from_dockstore2.png "Terra import from Dockstore prompt")

*Figure 2: WDL workflow import*

You will need to pick a workspace to export it into. You can either
select an existing workspace or create a new one.

Then hit the "Import" button and continue from within the Terra
interface to configure and run your workflow.

Note that you may want to double-check that the workflow specifies a
runtime environment (docker, cpu, memory, and disks) to avoid using
limiting defaults on Terra. See more [here](https://cromwell.readthedocs.io/en/stable/wf_options/Overview/).

## WDL Workflows Limitations

1. While we support launching of WDL workflows, tools as listed in Dockstore are currently not supported.
2. Terra does not currently support file-path based imports. Importing a workflow with file-based imports will result in error. See the [converting file-based imports doc](https://docs.dockstore.org/en/develop/end-user-topics/language-support.html#converting-file-path-based-imports-to-public-http-s-based-imports-for-wdl) for more info.
3. Only the WDL language is supported.

## See Related Documentation

- [AWS Batch](https://docs.dockstore.org/en/develop/advanced-topics/aws-batch.html)
- [Azure Batch](https://docs.dockstore.org/en/develop/advanced-topics/azure-batch.html)
- [DNAnexus Launch With](https://docs.dockstore.org/en/develop/launch-with/dnanexus-launch-with.html)
- [DNAstack Launch With](https://docs.dockstore.org/en/develop/launch-with/dnastack-launch-with.html)
