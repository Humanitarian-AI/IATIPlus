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

## Scrapping File URLs and Metadata

Basic information on publishing organizations and their datasets including file URLs and when the files were last updated can be sourced manually through scrapping the IATI Registry and potentially through other IATI [data sources](https://iatistandard.org/en/using-data/). While we research how to aquire the URL addresses of all known XML files published by organizations and when they were last updated through other means, Sprint 01 will concentrate on aquiring the information directly through manual scrapping.

![CARE Nepal Datasets](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/CARENepal_datasets.png)

Our scrapper will navigate to each organization's **Datasets** page on the IATI Registry, listed on IATI's Publishers List. For reference (see above) we will use CARE Nepal's [publisher entry](https://www.iatiregistry.org/publisher/?q=cnepal&sort=title+asc) as an example.

![CARE Nepal Files](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/CARENepal_files.png)

Organization datasets pages, like CARE Nepal's [datasets page](https://www.iatiregistry.org/publisher/cnepal) list all of the organization's files. Each file entry contains a unique file name and information on when the file was last updated, the number of different activities detailed in the file and the file's URL address (the Download link navigates directly to the file URL).

![CARE Nepal Metadata](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/CARENepal_metadata.png)

Much of the same information can be accessed by navigating through the **Metadata** link. Uniquely, the metadata page will include information on when the IATI registry was last updated in addition to when the file's data was updated. See [metadata](https://www.iatiregistry.org/dataset/cnepal-activities) referencing the first file listed on CARE Nepal's datasets page above. Because organizations can fail to accruately indicate when activity information was last updated and there can be inconsistances between dates, Sprint 01 will undertake to collect different update datetime information.
