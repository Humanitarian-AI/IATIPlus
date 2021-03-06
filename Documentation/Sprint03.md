# Sprint 03

![IATI Plus Database](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/IATIPlus_sprints.png)

**Sprint 03** will concentrate on researching and establishing a working graph structure for IATI Plus and on setting up the database.

## Graph Structure

We need to consider how to optimally organize the orientation of IATI Plus' nodes and relationships and run some test queries on the database evaluating different configurations. Graphical structure will closely mirror ways IATI XML data is [formatted](https://iatistandard.org/en/iati-standard/203/activity-standard/example-xml/). As part of this work, we need to convert IATI XML element and attribute fields into suitable graph labels and properties.

![IATI Plus Fields](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/IATIPlus_fields_sheet.png)

This [Google Doc](https://docs.google.com/spreadsheets/d/1mj63wdGwZRJ7STbadU4r_fxtL0WtVK-D0qKS35rIBcQ/edit?usp=sharing) (shown above) lists all of IATI's information fields that we need to convert into suitable IATI Plus graph labels and properties. Field hierarchy and XML paths are included to aid conversion work. See [issue](https://github.com/Humanitarian-AI/IATIPlus/issues/8) for more inforamtion.

## Database Setup and Operations

We need to administratively setup the database, setup user permissions, populate the database with an initial IATI corpus and tackle how researchers and applications can query the database and interact with it.

But through development and testing we will practice uploading small data sample sets beginning with IATI's list of publishers (see Sprint 01) and IATI generated example organization and activity files.
