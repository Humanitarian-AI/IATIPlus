# Sprint 01: Create an IATI Publisher List

![IATI Plus Database](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/IATIPlus_sprints.png)

**Sprint 01** will concentrate on creating foundational nodes (see red colored nodes) and relationships to build IATI Plus' graph database around.

Initiatives like the International Aid Transparency Initiative (IATI) and [ReliefWeb](https://reliefweb.int/organization/acmad) list organizations channeling information through their initiatives. ReliefWeb is the humanitarian community's most widely used jobs and information sharing portal while IATI is the humanitarian community's most widely used information sharing standard and publishing framework. IATI Plus will recognize IATI and initiatives like ReliefWeb as **groups** or associations linking together member organizations. Then IATI Plus will establish named entity nodes for all of IATI's publishing organizations and nodes for each organization's dataset page. These core nodes will create a foundation for sebsequent nodes and relationships.

## Publisher Information

![IATI Pulishers List](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Publishers_List.png)

The **IATI Registry** maintains an updated list of organizations channeling aid activity information through the framework. Organizations do this by means of publishing XML files on their web servers and then registering file URLs with IATI. Our first sprint (Sprint 01) will tackle how to extract and store up-to-date list information in our Neptune graph database, including all known XML file URL addresses which can be found via navigating through each organization's dataset page. For reference, Oxfam GB's datasets page can be found [here](https://iatiregistry.org/publisher/oxfamgb). Each dataset page lists one or more dataset files each with their own URL.

![Org and URL nodes](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Org_URLs.png)

Although the project will only add a comparatively small number of nodes (aprox 1400 organization nodes and nodes corresponding to list and URL information) and relationships to Neptune, as a starting point the sprint will help the team begin setting up IATI Plus' core AWS components and begin generating and testing code.

## Background

IATI Plus aims to store a fully up-to-date IATI corpus in a Neptune graph database to address deficiencies found in other IATI data sources, namely their inability to support reporting applications operating at scale and research projects.

Although initially we plan to rely on IATI’s daily dropbox data dump to source IATI information, we need to evaluate and develop our own reliable means of sourcing IATI data and one way involves tracking all known IATI XML files and extracting information from them. To this end we will need to store the location of all of these XML files in our database. Sprint 01 will generate and store these URLs and other information on found on IATI's Publisher List (org name, ID, Type, Headquarters Country, Number of Datasets and Links to their dataset pages).

## URL Addresses

Research by team members needs to be carried out to evaluate ways of soureing all known IATI XML file URLs using existing IATI [data sources](https://iatistandard.org/en/iati-tools-and-resources/) such as IATI's Datastore. See [issue]() linked to this need.

Manually, XML file URLs can be extracted via navidating through IATI's Registry and organization datasets. Other useful information can be extracted as well including when IATI file information was last updated.

#### Organization Dataset Page

![Org File](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Org_File.png)

Using Oxfam GB's [Datasets Page](https://www.iatiregistry.org/publisher/oxfamgb) for reference, individual files can be found listed like this (above). The entries contain links to file metadata, the file's URL (download link) to database in Neptune, and to other information.

#### Organization File Metadata

![Org Metadata](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/Org_Metadata.png)

Navigating to a file's metadata page will provide information on when the file and regitery were last updated, to database in Neptune along with how many individual activities are detailed in the file.

## Sprint 01, Sprint 02 and Sprint 03

![Datasets Graph](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/File_Data.png)

**Sprint 01** will graph information on organizations channeling information through IATI, information listed on each organization found on IATI's publisher list and include all known file URLs and associated file metadata. **Sprint 02** and **Sprint 03** will extract and store information contained in actual organization XML files. For reference, here is Oxfam GB's Afghanistan IATI XML [file](http://iati.oxfam.org.uk/xml/oxfamgb-af.xml) listing individual activities and activity XML elements and attributes.

## AWS Components

Sprint 01 will require setting up the Neptune database and doing some basic formatting on it and setting up either Lambda or EC2 to store executable code.
