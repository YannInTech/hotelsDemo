### Hotels sample Search application for Azure AI with search.documents and storage.blob Azure Python SDKs

## Description

![schema](skill-archi.png)

The present notebook contains python code leveragin the Azure Python SDK to host, enrich and expose to a search client an example database of Hotels presenting various characteristics. It leverages Azure blob containers for ingesting a source .json file in a first step. Next, Enrichment uses an indexer composer with a datasource, index and skillset to populate the custom index with augmented content. Search agents can be instantiated to search the index once it is deployed.
The given code deploys and configures all required ressources via the Azure Python SDK.

## Requirements

Please create a virtual environment with the provided environmt.yml and populate a .env with required Azure microservices keys. You may edit and rename the .txt provided.

azure-search-documents >= 11.4.0
azure-storage-blob >= 12.19.0