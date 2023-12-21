### Hotels sample Search application for Azure AI with search.documents and storage.blob Azure Python SDKs

## Description

The present Jupyter notebook contains the source code for uploading to an Azure storage service container a .json data file.  
This file is indexed by creating documents for every line entry in its content before being queried via keyword, filtered, sorted and faceted searches.  

The commands to create, load and query documents are using the azure-search-documents and azure-storage-blob Python SDKs  

Note: a .env file (no filename, only the extension) is required and must be located in the same folder as this notebook to refer the authentificaiton keys and service endpoints.
An empty example file to be populated is provided.

Separate functions to upload a source .json file to a storage service container, to create a dataSource, Index and Skillset to be passed to an Indexer are declared.  
Although the currently valid solution directly uses the local .json to populate the index created via the create_index function as the Pyhton SDK has at this time a known issue with using indexers via the Python SDK. When using azure-search-documents to create an Indexer, advanced properties could not be set for an indexer with a data connection of Azure Blob or Azure SQL Server. (https://github.com/Azure/azure-sdk-for-python/pull/33357)  

The advanced properties such as a configured skillset can enable AI enrichment and set up features such as multi language querying and translation.  
Another path is to use OpenAI service via vector dense embeddings queries which do not require AI enrichment and can leverage OpenAI models for multi language querying via token embeddings. Future development, OpenAI licensing permitting will use this approch.  

Several example queries are presented against the populated index via simple keyword search in the English language via the fields decalred as searchable in th eindex construction.  
The examples make use of the built configuration of the index in order to sort, filter and return an multi faceted presentation of search results.  