# Sprint 01: Create an IATI Publisher List

![IATI Plus Database](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/IATIPlus_sprints.png)

**Sprint 01** will concentrate on creating and keeping core foundational nodes (see red colored nodes and relationships) up-to-date, which IATI Plus' graph database will be built around.

## Core Structure

Initiatives like the International Aid Transparency Initiative (IATI) and [ReliefWeb](https://reliefweb.int/organization/acmad) list organizations channeling information through their initiatives. ReliefWeb is the humanitarian community's most widely used jobs and information sharing portal while IATI is the humanitarian community's most widely used information sharing standard and publishing framework. IATI Plus will recognize IATI and initiatives like ReliefWeb as **groups** or associations linking together member organizations. Then IATI Plus will establish named entity nodes for all of IATI's publishing organizations and nodes for each organization's dataset page. These core nodes will create a foundation for subsequent nodes and relationships generated from aid activity data stored in organization XML files (Sprint 02).

Core nodes will be formatted and organized around storing information extracted from IATI's Publisher List. The same structure will be replicated to store information extracted from other organization groupings and their publisher lists, for example from ReliefWeb.

## Publisher Information

![IATI Pulishers List](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Publishers_List.png)

The **IATI Registry** maintains an updated [list](https://www.iatiregistry.org/publisher/) of organizations channeling aid activity information through the framework. Sprint 01 will tackle how to extract and store up-to-date list information in our Neptune graph database. As a side project Sprint 01 will try to extract from the IATI Registry all known organization XML file URL addresses which can be found via navigating through each organization's dataset page. For reference, Oxfam GB's datasets page can be found [here](https://iatiregistry.org/publisher/oxfamgb). Each dataset page lists one or more dataset files each with their own URL.

See related [issue](https://github.com/Humanitarian-AI/IATIPlus/issues/9).

## Sprint 01 Nodes

![Org and URL nodes](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Sprint01_nodes.png)

On a granular level, Sprint 01 will create approximately 1400 organization **entity** nodes and a corresponding number of **datasets page** nodes. Entity nodes will include properties found on IATI's Publisher List and break out a datasets page node with the page's URL address as a property. The page nodes will branch out nodes corresponding to XML files published by the organizations each with their own unique URL address as a property.

Although the project will only add a comparatively small number of nodes and relationships to Neptune, as a starting point the sprint will help the team begin setting up IATI Plus' core AWS components and begin generating and testing code.

## Scrapping File URLs and Metadata

Basic information on publishing organizations and their datasets including file URLs and when the files were last updated can be sourced manually through scrapping the IATI Registry and potentially through other IATI [data sources](https://iatistandard.org/en/using-data/). While we research how to acquire the URL addresses of all known XML files published by organizations and when they were last updated through other means, Sprint 01 will concentrate on acquiring the information directly through manual scrapping.

![CARE Nepal Datasets](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/CARENepal_datasets.png)

Our scrapper will navigate to each organization's **Datasets** page on the IATI Registry, listed on IATI's Publishers List. For reference (see above) we will use CARE Nepal's [publisher entry](https://www.iatiregistry.org/publisher/?q=cnepal&sort=title+asc) as an example.

![CARE Nepal Files](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/CARENepal_files.png)

Organization datasets pages, like CARE Nepal's [datasets page](https://www.iatiregistry.org/publisher/cnepal) list all of the organization's files. Each file entry contains a unique file name and information on when the file was last updated, the number of different activities detailed in the file and the file's URL address (the Download link navigates directly to the file URL).

![CARE Nepal Metadata](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/CARENepal_metadata.png)

Much of the same information can be accessed by navigating through the **Metadata** link. Uniquely, the metadata page will include information on when the IATI registry was last updated in addition to when the file's data was updated. See [metadata](https://www.iatiregistry.org/dataset/cnepal-activities) referencing the first file listed on CARE Nepal's datasets page above. Because organizations can fail to accurately indicate when activity information was last updated and there can be inconsistancies between dates, Sprint 01 will undertake to collect different update datetime information.

## Proposed: IATI Plus Sprint 01 Labels and Properties

Work needs to be carried out to consider and establish node and relationship fields and their label and property names. IATI Plus will primarily extract and check information from IATI data sources and directly from organizations XML files to keep its database up-to-date. Sprint 01 will extract separate information directly from the IATI registry to form a framework to branch XML files to, files which will constantly refresh.

![Sprint 01 Nodes and Labels](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Sprint01_labels.png)

As an idea, to separate foundational data from XML data and to create a multi-purpose foundational graphical structure, we'd like to propose using the following structure, nodes, labels and properties as a starting point. The actual label and property names will need to be edited to suite proper naming conventions though.

Entity metadata will come from IATI's Publisher List while File metadata will come from organization dataset pages. Each XML file will link to it's own File metadata node. Pairing File metadata nodes with XML File nodes (actual XML files published by organizations) will make it possible to compare data-time information for accuracy and give IATI Plus a metadata node to add potential new properties to for studying. This overall structure will suit future plans to add data from ReliefWeb to IATI Plus and data from other groupings linking organizations.

Label | Properties | Note
--- | --- | ---
Group | | Node starting point to branch different groups
Entity | | Group node label
" | group : IATI | Group name property
" | name : CARE Nepal | Organization name property
Entity metadata | | Entity metadata node label
" | identifier : xyz123 | IATI Org Identifier property
" | type : NGO | Type of organization property selected from an IATI codelist
" | country : Nepal | Country property selected from an IATI codelist
" | datasets : 12 | Number property of separate files published by the organization each with their own URL
Entity datasets | | Datasets node label
" | datasets url : http:// | Organization's datasets page URL property listing all files published by the organizations
File metadata | | Individual file metadata node label
" | file title : Example File Title | Title property of the file
" | file URL : http:// | File URL address property
" | last-update : 2019-07-12 09:47 | The most resent date and time property that a file was updated
" | last registry update : 2019-08-11 10:17 | The most recent registry update property
XML file | | XML file stored on organization server

