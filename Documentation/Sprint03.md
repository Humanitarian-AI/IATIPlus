# Sprint 03

![IATI Plus Database](https://github.com/Humanitarian-AI/IATIPlus/blob/main/Media/IATIPlus_sprints.png)

**Sprint 03** will concentrate on researching and establishing a working graph structure for IATI Plus and on setting up the database.

## Graph Structure

We need to consider how to optimally organize the orientation of IATI Plus' nodes and relationships, generate a list of all of its labels and properties based closely on IATI XML elements and attributes and run some test queries on the database evaluating different configurations.

We also need to generate a conversion table matching IATI XML fields with IATI Plus labels and properties suitable for our graph database and Neo4j Cypher / Open Cypher naming conventions. See task [issue](https://github.com/Humanitarian-AI/IATIPlus/issues/8).

## Database Setup and Operations

We need to administratively setup the database, setup user permissions, populate the database with an initial IATI corpus and tackle how researchers and applications can query the database and interact with it.
