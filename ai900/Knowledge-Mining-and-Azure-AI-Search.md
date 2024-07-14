# Knowledge Mining and Azure AI Search
> Azure AI Search makes your data searchable.

**Knowledge mining**: extracting information from large volumes of often unstructured data.

**Azure AI Search** is a cloud search service that has tools for building user-managed indexes.
- PaaS solution managed by Microsoft
- 99.9% uptime SLA available
- Provides programmable search engine built on Apache Lucene
- Indexes can be:
    - Internal only use
    - Enable searchable content on public-facing internet assets
- Utilizes built-in capabilities of Azure AI services
    - Image processing
    - Content extraction
    - Natural language processing

Resource: [Azure AI Search]()

## Azure AI Search features
Azure AI Search features:
- **Data from any source**: accepts data from any source provided in JSON format
    - Includes `auto crawling support` for selected data sources in Azure
- **Full text search and analysis**: offers full text search capabilities
    - Supports simple query and full Lucene query syntax
- **AI powered search**: built-in Azure AI capabilities for image and text analysis from raw content
- **Multi-lingual**: 56 languages 
- **Geo-enabled**: geo-search filtering based on proximity to a physical location
- **Configurable user experience**: improve the user experience including autocomplete, autosuggest, pagination, and hit highlighting

**Data source** contains the data artifacts you want to search.
- Options
    - Hierarchy of folders and files in Azure Storage
    - Text in a database such as Azure SQL Database or Azure Cosmos DB
- Only JSON is supported

**Indexes** contain your persisted fields/content are persisted in an index
- Can be searched by client applications
- The fields are used for searching, filtering, and sorting to generate a set of results that can be displayed or otherwise used by the client application.

> Indexes are like a container of searchable documents

**Index Schema**: definition of the structure of the data in the indexed documents

![Sample index](../assets/ai900/json-index-example.png "Sample index")

**Index attributes** describe how you would like to search and display the fields in the documents
- Examples:
    - Sortable
    - Facetable
    - Filterable
- Most efficient indexes `use only the behaviors that are needed`

**Indexers** automate data ingestion
- JSON serialization of source data in native formats
- Connects to a data source, serializes the data, and passes to the search engine for indexing
- Most support change detection for simpler refresh
- Support data enrichment
    - Attach a skillset that applies a sequence of AI skills to enrich the data
    - Make it more searchable
    - Enriched content can be sent to a knowledge store, which stores output from an AI enrichment pipeline in tables and blobs in Azure Storage for independent analysis or downstream processing

### Loading data into index
Transform original documents into JSON before loading into an index
- **Push method**: JSON data is pushed into a search index
    - Methods:
        - REST API 
        - .NET SDK
    - Most flexible as no restrictions on the data source type, location, or frequency of execution
- **Pull method**: Indexers can pull data from popular Azure data sources
    - If not JSON, can export data into JSON 
    - Indexer is a crawler that extracts searchable text and metadata from data source
    - Populates a search index using field-to-field mappings

## Define an enrichment pipeline
**AI enrichment**: embedded image and natural language processing in a pipeline that extracts text and information from content that can't otherwise be indexed for full text search.

**Skillset** defines the operations that extract and enrich data to make it searchable. 
- AI skills can be:
    - Built-in skills
        - NLP skills
            - Key phrase extraction
            - Text translation
        - Image processing skills
            - OCR
            - Image analysis
    - Custom skills

## Data import monitoring and verification
Search services overview page has a dashboard to monitor health and stats
- Document count
- Indexes used
- Storage used

Indexers only import new or updated documents, so it is normal to see zero documents indexed.

Have to drop and recreate indexes if you need to make changes to field definitions.
- Better with code-based approach
- Create new index (by name), using same indexer
- Reference new index with code

Focus of an Azure AI Search solution is usually to `create a searchable index`, you can also take advantage of its data extraction and enrichment capabilities to `persist the enriched data in a knowledge store` for further analysis or processing.

A knowledge store can contain one or more of three types of projection of the extracted data:
- **Table projections** used to structure the extracted data in a relational schema for querying and visualization
- **Object projections** are JSON documents that represent each data entity
- **File projections** used to store extracted images in JPG format

## Query data in an Azure AI Search index
Schema of the index determines what queries can be answered.

Queries can be submitted as an HTTP or REST API request, with the response coming back as JSON.

[Simple query](https://learn.microsoft.com/en-us/azure/search/query-odata-filter-orderby-syntax) or full Lucene syntax

**Simple query example:** \
`coffee (-"busy" + "wifi")` \
Find content about coffee, excluding busy and including wifi.
