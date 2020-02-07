---
description: >-
  An explanation for the interactive Data Dictionary page on Gen3 BioData
  Catalyst.
---

# Dictionary

The Gen3 BioData Catalyst Dictionary contains the visualization of the BioData Catalyst data model. When first navigating to the page, it will default to the graph view, which display the relationships between nodes. It will display whether the links between nodes are required or optional links and node types, which is noted in the right corner legend.

![The interactive BioData Catalyst Data Dictionary without anything selected.](../../.gitbook/assets/image%20%2817%29.png)

## Graph View

To learn more about the node in the Graph View, a user can click on a node. This will initially highlight the relational paths that can be taken to connect to the node to the program node. A "Data Model Structure" list will also appear on the left side toolbar. This will write the node path that is required to reach the node from the program node.

![An example of a node being selected in the interactive graph view.](../../.gitbook/assets/image%20%285%29.png)

When another node in the path is selected, it will then gray out the other possible paths and only highlight the selected path. It will also change the node path on the left side toolbar.

![An example of a second node being selected in the path of the first selected node.](../../.gitbook/assets/image%20%2814%29.png)

The left side toolbar has two options available, `Open properties` and `Download templates`. The `Download templates` option will download the submission files for all the nodes in the chain. The `Open properties` option, will open the node properties in a new pop-up window.

![A node&apos;s property window.](../../.gitbook/assets/image%20%2823%29.png)

This property view will display all properties in the node and information about each property:

* **Property**: Name of the property.
* **Type**: The type of input for the node. Examples of this are string, integer, Boolean and enumerated values, which are displayed as preset strings.
* **Required**: This field will display whether the property is required for the submission of the node into the data model.
* **Description**: This field will display further information about the property.
* **Terms**: This field can be populated with external resources that have further information about the property.

## Table View

The Table View is similar to the Properties view, and nodes are displayed as a list of entries grouped by their node category.

![Table View of the Gen3 BioData Catalyst Data Dictionary.](../../.gitbook/assets/image%20%2812%29.png)

Clicking on one of the nodes will then open the Properties view of the node.

![Opening the Properties in the Table View format.](../../.gitbook/assets/image%20%2819%29.png)

## Dictionary Search

The Data Dictionary also contains a search function that will look through not only the names of the properties but the description as well. When the search function is used, it will default to the graph model as it will highlight nodes that contain the search term.

![An example search for the term &quot;Harmonized&quot;](../../.gitbook/assets/image%20%2825%29.png)

Clicking on one of these nodes, it will only display the properties that have this keyword present in either the property name or the description.

![The Laboratory Results node with only properties that contain the term &quot;Harmonized&quot;.](../../.gitbook/assets/image%20%2811%29.png)

This search is then saved for later recovery in the "Last Search" list, with the number of nodes the term was found in.

