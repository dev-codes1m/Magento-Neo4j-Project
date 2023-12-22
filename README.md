```markdown

# Dockerized Magento and Neo4j Deployment

This repository provides Docker Compose files for deploying Bitnami Neo4j and Magento containers. Follow the steps below to set up and run the applications on your local machine or any cloud-based platform.
Make a command docker-compose up -d to run the dockerfile on Cloud-Based Platform or Local Deployment In Local Docker Because of '' Charges Incurred On The Cloud-Based This Project is Deployed On Local Docker Desktop Recorded Video Are Uploaded On YouTube

Link1 (Magento Deployement And Working): 

Link2(Neo4j Deployment And Working):


## Prerequisites

- Docker installed on your machine.

## Deployment

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/your-repo.git](https://github.com/dev-codes1m/Magento-Neo4j-Project.git

   ```

2. Deploy Magento:

   ```bash
   cd magento
   docker-compose up -d
   ```

   Access Magento at [http://localhost](http://localhost/admin).

3. Deploy Neo4j:

   ```bash
   cd neo4j
   docker-compose up -d
   ```

   Access Neo4j at [http://localhost:7474](http://localhost:7474).

### Steps for Magento File Uploadation:

1. Upload at least one product on the Magento platform.

2. Download the CSV file from the export section in settings.

3. Transform the data using Python and save it as `Processing.ipynb`.

4. Import the transformed data back into Magento.

5. Your products are now ready to be displayed on the Magento e-commerce website.

6. Magento Products Uploaded ScreenShot in The Folder 'Magento_Products_ScreenShots'

![File Uploaded Successfully](https://github.com/dev-codes1m/Magento-Neo4j-Project/blob/main/Magento_Products_ScreenShots/Screenshot%20(423).png)
![Products Uploaded Info](https://github.com/dev-codes1m/Magento-Neo4j-Project/blob/main/Magento_Products_ScreenShots/Screenshot%20(424).png)

### Steps for Neo4j Data Uploadation:

1. Install Neo4j in Docker using the provided Docker Compose file.

2. Set the default username to `neo4j` and password to `neo4j`.

3. Upload your data to the Neo4j database using Cypher queries.

   Example:

   ```cypher
   LOAD CSV WITH HEADERS FROM 'file:///final_product.csv' AS row
   MERGE (m:Manufacturer {name: row.manufacturer})
   CREATE (p:Product {
     name: row.name,
     short_description: row.short_description
   })
   MERGE (p)-[:MANUFACTURED_BY]->(m);
   ```

   Search for more Cypher queries in the [Neo4j Cypher Guide](https://neo4j.com/docs/cypher-manual/current/).

4. Project screenshots are available in the folder 'Neo4j Screenshot Graphs'.

   ![Neo4j](https://github.com/dev-codes1m/Magento-Neo4j-Project/blob/main/Products_Neo4j_ScreenShots/Relation%20Between%20Products%20And%20Manufactorers.png)

## References:
   Magento Download: https://bitnami.com/stack/magento
   Neo4j Download: https://bitnami.com/stack/neo4j
   Tutorials: Youtube
   Cypher_Query: [Neo4j Cypher Guide](https://neo4j.com/docs/cypher-manual/current/introduction/)
## Contributing

If you'd like to contribute, please fork the repository and create a new branch. Pull requests are welcome!

