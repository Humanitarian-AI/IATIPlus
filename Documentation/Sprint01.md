# Sprint 01: Create an IATI Publisher List

![IATI Plus Database](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/IATIPlus_sprints.png)

**Sprint 01** will concentrate on creating foundational nodes (see red colored nodes) and relationships to build IATI Plus' graph database around.

Initiatives like the International Aid Transparency Initiative (IATI) and [ReliefWeb](https://reliefweb.int/organization/acmad) list organizations channeling information through their initiatives. ReliefWeb is the humanitarian community's most widely used jobs and information sharing portal while IATI is the humanitarian community's most widely used information sharing standard and publishing framework. IATI Plus will recognize IATI and initiatives like ReliefWeb as **groups** or associations linking together member organizations. Then IATI Plus will establish named entity nodes for all of IATI's publishing organizations and nodes for each organization's dataset page. These core nodes will create a foundation for subsequent nodes and relationships.

## Publisher Information

![IATI Pulishers List](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Publishers_List.png)

The **IATI Registry** maintains an updated [list](https://www.iatiregistry.org/publisher/) of organizations channeling aid activity information through the framework. Sprint 01 will tackle how to extract and store up-to-date list information in our Neptune graph database. As a side project Sprint 01 will try to extract from the IATI Registry all known organization XML file URL addresses which can be found via navigating through each organization's dataset page. For reference, Oxfam GB's datasets page can be found [here](https://iatiregistry.org/publisher/oxfamgb). Each dataset page lists one or more dataset files each with their own URL.

## Sprint 01 Nodes

![Org and URL nodes](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Sprint01_nodes.png)

On a granular level, Sprint 01 will create aproximately 1400 organization **entity** nodes and a corresponding number of **datasets page** nodes. Entity nodes will include properties found on IATI's Publisher List and break out a datasets page node with the page's URL address as a property. The page nodes will branch out nodes corresponding to XML files published by the orgabnizations each with their own unique URL address as a property.

Although the project will only add a comparatively small number of nodes and relationships to Neptune, as a starting point the sprint will help the team begin setting up IATI Plus' core AWS components and begin generating and testing code.

## Org and Activity File URL Addresses

Research by team members needs to be carried out to evaluate ways of sourcing all known IATI XML file URLs using existing IATI [data sources](https://iatistandard.org/en/iati-tools-and-resources/) such as IATI's Datastore. See [issue]() linked to this need.

Manually, XML file URLs can be extracted via navigating through IATI's Registry and organization datasets. Other useful information can be extracted as well including when IATI file information was last updated.

#### Organization Dataset Page

![Org File](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Org_File.png)

Using Oxfam GB's [Datasets Page](https://www.iatiregistry.org/publisher/oxfamgb) for reference, individual files can be found listed like this (above). The entries contain links to file metadata, the file's URL (download link) to database in Neptune, and to other information.

#### Organization File Metadata

![Org Metadata](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Org_Metadata.png)

Navigating to a file's metadata page will provide information on when the file and registry were last updated, to database in Neptune along with how many individual activities are detailed in the file.
