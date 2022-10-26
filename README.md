![IATI Plus](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/IATIPlus_Banner.png)

The [Humanitarian AI](https://humanitarianai.org/) meetup community is launching a **call-to-action** seeking volunteers to work on quickly setting up a new IATI database to support relief efforts aiding Ukrainian refugees and IDPs.

## Project

IATI is a reporting framework humanitarian organizations use to openly share information on aid activities, transactions and results in granular detail. Reporting activities in compliance with IATI helps improve operational transparency, benefitting operational planning, fundraising and coordination across organizations, digital applications, and crisis theaters.

The framework is managed by the [International Aid Transparency Initiative](https://iatistandard.org/en/), supported by the United Nations, mandated by many government development agencies and used today by over 1400 organizations and donors to store information on over 1 million aid activities. Although IATI was originally setup in 2008 to track development aid flows, it has evolved to become a general use reporting framework and the best source of highly structured aid activity information accessible to machine applications

Our new database (**IATI Plus**) will help make reporting aid activities by organizations responding to the Ukrainian crisis easier, make more IATI data searchable and usable compared to other IATI data sources and provide developers with a better IATI data source for applications. Uniquely, the database will also be able to handle experimental IATI elements and attributes, store both IATI and non-IATI data, and allow individuals and teams to securely view, edit, and work simultaneously on generating and updating activity files, making reporting and sharing information faster, more inclusive and responsive to needs on the ground.

## Problem and Solution

On a technical level, organizations report activities by storing information on their web servers converted into XML code using the [IATI Standard](https://iatistandard.org/en/iati-standard/), then organizations share file metadata with the [IATI Registry](https://www.iatiregistry.org/), making all the information aggregatable, searchable and usable to power a broad range of applications. For reference, an actual activity file containing information on five activities carried out by Oxfam GB in Senegal can be found [here](http://iati.oxfam.org.uk/xml/oxfamgb-sn.xml).

IATI data can be accessed directly stored on organization servers or through a host of registries, datastores and APIs but these [resources](https://iatistandard.org/en/iati-tools-and-resources/) aren’t setup to power sophisticated consumer grade reporting applications operating at scale or to support the training and testing of machine learning models.

**IATI Plus** will contribute to addressing these problems and help spur and support the development of new humanitarian-data-powered applications, including virtual assistants and artificial intelligent applications.

## Documentation

The project is organized around **Sprints**. These will mainly work on setting up and testing different aspects of creating a sophisticated new **graph database** to store aid activity information and an accompanying **user interface**. While a connected sprint will organize and run a [Data Partners Program](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Documentation/DataPartners.md).

Detailed information on sprints is stored in the project's [Documentation](https://github.com/Humanitarian-AI/IATIPlus/tree/main/Documentation) folder. We will be experimenting with using GitHub [Projects](https://github.com/orgs/Humanitarian-AI/projects/2), [Milestones](https://github.com/Humanitarian-AI/IATIPlus/milestones) and [Issues](https://github.com/Humanitarian-AI/IATIPlus/issues) to help document and coordinate the project. 

## Get Involved
We're seeking volunteers of all levels to help work on the database and user interface and on helping humanitarian organizations and grassroots aid initiatives responding to the war and humanitarian crisis in Ukraine channel information on their activities and needs through IATI and IATI Plus.

To join the project and the project's Slack workspace or to learn more about the project, contact: **team** (at) **humanitarianai.org**

## Contribute

The project is an all-volunteer open source initiative. It is supported by cloud computing and data storage credits provided by tech companies. Contributions to help cover other expenses can be made through [GitHub Sponsors](https://github.com/sponsors/Humanitarian-AI) and [Open Collective](https://opencollective.com/humanitarian-ai/projects/iati-plus).
