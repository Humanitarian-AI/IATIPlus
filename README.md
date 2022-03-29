# IATI Plus: Neptune Database for Aid Activity Information

The Humanitarian AI meetup community is launching a community-wide call-to-action seeking volunteers to work on quickly setting up a new hybrid IATI database to help support relief efforts aiding Ukrainian refugees and IDPs (internally displaced persons).

IATI is an open data sharing (XML) standard and reporting framework humanitarian organizations use to report aid activities, transactions and results. Reporting activities in compliance with IATI makes granular information on activities visible to other organizations and to machine applications, improving operational planning, fundraising and coordination in the field. However, IATI's backend infrastructure is not setup to handle reporting and querying at a scale, sufficient to adequately support the sheer number of organizations and initiatives responding to the Ukrainian humanitarian crisis.

As a proof-of-concept and with the help of computing credits provided by Amazon, volunteers will undertake to setup a powerful new graph database to store and make IATI data accessible to humanitarian organizations and donors in way capable of meeting today's technical needs.

## Database Basics

At heart **IATI Plus** is an extensible IATI database. It will store a daily-updated copy of IATI's entire corpus (12GB and growing) and additional traversable  information. Specifically the database will give organizations the ability to test adding non-IATI information fields to their aid activity files, providing extra granular information and give organizations and initiatives the ability to add additional data and additional codelists and correlation tables to the database, creating extra nodes and relationships expanding the database's question-answering potential.

## Mission

We aim to see if we can incentivize more organizations to report their aid activities, make reporting easier and improve the use and impact of data on relief efforts through our volunteer project.

## Get Involved

The Humanitarian AI meetup community is seeking volunteers of all levels to help work on setting up **IATI Plus** and on helping organizations channel aid activity information through the database and use it. To join the project, contact: **team (at) humanitarianai.org**

Project task list: https://github.com/Humanitarian-AI/IATIPlus/blob/main/Tasks.md
