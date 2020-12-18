---
description: The interactive Data Dictionary page on the BioData Catalyst Gen3 platform
---

# Dictionary

The Dictionary page contains an interactive visual representation of the Gen3 data model. The default graph model view, as seen below, displays all of the nodes and relationships between nodes in a hierarchical structure. The model further specifies the node types and links between nodes, as highlighted in the legend \(top right-hand side of the Data Dictionary page\).

![The default view of the interactive Gen3 Data Dictionary.](../../.gitbook/assets/bdc_dec20_graph_dd.png)

## Graph View

Users can click on any of the graph nodes in order to learn more about their respective properties. By clicking on a node,  the graph will highlight that specific node and all associated links that connect it to the Program node. A "Data Model Structure" list will also appear on the left side toolbar. This will display the node path required to reach the selected node from the Program node.

![An example of a node being selected in the interactive graph view.](../../.gitbook/assets/bdc_dec20_graph_dd_detail.png)

When a second node in the path is selected, it will then gray out the other possible paths and only highlight the selected path. It will also change the "Data Model Structure" list on the left side toolbar.

![An example of a second node being selected in the path of the first selected node.](../../.gitbook/assets/bdc_dec20_graph_dd_detail2.png)

The left side toolbar has two options available, `Open properties` and `Download templates`. The `Download templates` option will download the submission files for all the nodes in the "Data Model Structure" list. The `Open properties` option will open the node properties in a new pop-up window. The `Open properties` button can also be found on the node that was first selected. 

![A node&apos;s property window.](../../.gitbook/assets/image%20%288%29.png)

This property view will display all properties in the node and information about each property:

* **Property**: Name of the property.
* **Type**: The type of input for the node. Examples of this are `string`, `integer`, `Boolean` and enumerated values \(`enum`\), which are displayed as preset strings.
* **Required**: This field will display whether the property is required for the submission of the node into the data model.
* **Description**: This field will display further information about the property.
* **Term**: This field can be populated with external resources that have further information about the property.

## Table View

The Table View is similar to the Properties view, and nodes are displayed as a list of entries grouped by their node category.

![Table View of the Gen3 Data Dictionary.](../../.gitbook/assets/bdc_dec20_table_dd.png)

Clicking on one of the nodes will open the Properties view of the node.

![Opening the Properties in the Table View format.](../../.gitbook/assets/bdc_dec20_table_props.png)

## Dictionary Search

The Dictionary contains a text-based search function that will search through the names of the properties and the descriptions. While typing, a list of suggestions appears below the search bar. Click on a suggestion to search for it.

![An example search for the term &quot;study&quot;. Search results appear under the search bar while typing.](../../.gitbook/assets/bdc_dec20_search_1.png)

When the search function is used, it will default to the graph model and highlight nodes that contain the search term. Frames around the node boxes indicate whether the searched word was identified in the name of the node \(full line\) or in the node's  description and properties' names/descriptions \(dashed line\). 

![Search results for &quot;study&quot; in the Graph View. ](../../.gitbook/assets/bdc_dec20_search_2.png)

Clicking on one of these nodes, it will only display the properties that have this keyword present in either the property name or the description.

![Search results are highlighted in orange color.](../../.gitbook/assets/bdc_dec20_search_3.png)

Click "Clear Search Result" to wipe the free text search if needed.

![Clear the search results if needed.  ](../../.gitbook/assets/bdc_dec20_search_4.png)

The search history is saved below the search bar in the "Last Search" list. Click on an item here to display the results again. Click "Clear History" if needed.

