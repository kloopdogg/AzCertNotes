# Storage

## Storage accounts
- Must have a globally unique name
- Provide over-the-internet access worldwide
- Determine storage services and redundancy options

## Storage redundancy
Azure Storage always stores multiple copies of your data so that it's protected from planned and unplanned events, including transient hardware failures, network or power outages, and massive natural disasters. Redundancy ensures that your storage account meets its availability and durability targets even in the face of failures.

| <div style="padding: 10px; background-color: #0171E9; width: 90%; text-align: center;">Redundancy Configuration</div> | <div style="padding: 10px; background-color: #001021; width: 90%; text-align: center;">Deployment</div> | <div style="padding: 10px; background-color: #742373; width: 90%; text-align: center;">Durability</div> |
|----|----|----|
| Locally redundant storage (LRS) | Single datacenter in the primary region | 11 nines |
| Zone-redundant storage (ZRS) | Three availability zones in the primary region | 12 nines |
| Geo-redundant storage (GRS) | Single datacenter in the primary and secondary region | 16 nines |
| Geo-zone-redundant-storage (GZRS) | Three availability zones in the primary region and a single datacenter in secondary region | 16 nines |

## Azure storage services
- **Azure Blob:** optimized for storing massive amounts of unstructured data, such as text or binary data.
- **Azure Disk:** provides disks for virtual machines, applications, and other services to access and use.
- **Azure Queue:** message storage service that provides storage and retrieval for large amounts of messages, each up to 64KB.
- **Azure Files:** sets up a highly available network file share that can be accessed by using the Server Message Block protocol.
- **Azure Tables:** provides a key/attribute option for structured non-relational data storage with a schema-less design.

## Storage service public endpoints
| <div style="padding: 10px; background-color: #0171E9; width: 90%; text-align: center;">Storage service</div> | <div style="padding: 10px; background-color: #001021; width: 90%; text-align: center;">Public endpoint</div> |
|----|----|
| Blob Storage | https://\<storage-account-name>.blob.core.windows.net |
| Data Lake Storage Gen2 | https://\<storage-account-name>.dfs.core.windows.net |
| Azure Files | https://\<storage-account-name>.file.core.windows.net |
| Queue Storage | https://\<storage-account-name>.queue.core.windows.net |
| Table Storage | https://\<storage-account-name>.table.core.windows.net |

## Azure storage access tiers
You can switch between these access tiers at any time.

| <div style="padding: 10px; background-color: #0171E9; width: 150px; text-align: center;">Hot</div> | <div style="padding: 10px; background-color: #1058C2; width: 150px; text-align: center;">Cool</div> | <div style="padding: 10px; background-color: #423E9A; width: 150px; text-align: center;">Cold</div> | <div style="padding: 10px; background-color: #742373; width: 150px; text-align: center;">Archive</div> |
|----|----|----|----|
| Optimized for storing data that is accessed frequently. | Optimized for storing data that is infrequently accessed and stored for at least 30 days. | Optimized for storing data that is infrequently accessed and stored for at least 90 days. | Optimized for storing data that is rarely accessed and stored for at least 180 days with flexible latency requirements. | 

## Azure Migrate
Azure Migrate is a service that helps you migrate from an on-premises environment to the cloud.
- Unified migration platform
- Range of integrated and standalone tools
- Assessment and migration

## Azure Data Box
Azure Data Box is a physical migration service that helps transfer large amounts of data in a quick, inexpensive, and reliable way. The secure data transfer is accelerated by shipping you a proprietary Data Box storage device. The Data Box is transported to and from your datacenter via a regional carrier. A rugged case protects and secures the Data Box from damage during transit.
- Store up to 80 terabytes of data.
- Move your disaster recovery backups to Azure.
- Protect your data in a rugged case during transit.
- Migrate data out of Azure for compliance or regulatory needs.
- Migrate data to Azure from remote locations with limited or no connectivity.

## AzCopy
AzCopy is a command-line utility that you can use to copy blobs or files to or from your storage account. With AzCopy, you can upload files, download files, copy files between storage accounts, and even synchronize files. 

## Azure File Sync
Azure File Sync is a tool that lets you centralize your file shares in Azure Files and keep the flexibility, performance, and compatibility of a Windows file server.

## File management options

| <div style="padding: 10px; background-color: #0171E9; width: 90%; text-align: center;">AzCopy</div> | <div style="padding: 10px; background-color: #001021; width: 90%; text-align: center;">Storage Explorer</div> | <div style="padding: 10px; background-color: #742373; width: 90%; text-align: center;">Azure File Sync</div> |
|----|----|----|
| Command line utility | Graphical user interface (similar to Windows Explorer) | Synchronizes Azure and on- premises Windows File Server in a bidirectional manner |
| Copy blobs or files to or from your storage account | Compatible with Windows, MacOS, and Linux | Cloud tiering keeps frequently accessed files local, while freeing up space |
| One-direction synchronization | Uses AzCopy to handle file operations | Rapid reprovisioning of failed local server (install and resync) |