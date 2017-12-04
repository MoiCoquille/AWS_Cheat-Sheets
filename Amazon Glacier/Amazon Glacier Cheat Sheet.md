**Amazon Glacier Cheat Sheet**  
by Veronique Robitaille (v@indalit.com) 
  
**!!! Download PDF for single page formatting !!!** 

General Characteristics	|
----------------------- |
Data archiving and long-term backup.  Cold data	|
Data is copied to multiple devices within a facility and to multiple facilities. |
Data is stored in Archives which are then stored in	Vaults.	|
Durability 99.999999999% |
Synchronous for upload, asynchronous for download |
Only actions possible with Management Console are: |
   |	- Create Vault |
   |	- Delete Vault |
   |	*The rest with AWS CLI, REST API, SDKs |


Archives |
-------- |
Can be a single file or and aggregation of many in a 	
TAR or ZIP file. |
Maximum size is 40TB. |	
Immutable, once an Archive is created, it cannot be	
modified. |
Multipart Upload API starting at file size of 4GB. |
Unlimited number of Archives in a Vault	|
Archive Operations |
   |	- Upload, delete & set description |
Can perform Ranged Archive Retrievals; downloading only part of the archive. |
	

Vaults |
------ |
Vaults are containers that store Archives. |
Maximum 1000 Vaults per account	|
Vault Operations |
   |	- Create, delete, lock, list metadata, retrieve inventory, tag, configure notifications & set a description. |
Unique name within a region and per account	|
Can only delete an empty Vault.	|
Can retrieve Inventory, list & metadata. |
Can set tags to Vaults, maximum 50 per Vault. |
Access Policies from AWS resources and the internet. |
	
Retrieval Options |
----------------- |
Expedited |
   |	 - 1 to 5 minutes before download can start. |
   |     (1) On-demand: available most of the time |
   |     (2) Provisioned: guaranteed |
Standard |
   |     - 3 to 5 hours before download can start. |
Bulk |
   |	 - 5 to 12 hours before download can start. |


Encryption |
---------- |
Data at rest |
   |	 - Automatically encrypted using AES 256 bit symmetric keys. |
Data in transit	|
   |	 - Using SSL. |
	
Vault Inventory |
--------------- |
Inventory of all Archives in each Vault for DR or reconciliation purposes. |
Updated once a day. |
JSON or CSV file |
	
Mandatory Request Signing |
------------------------- |
All requests made to Glacier must be signed for authentication protection. |
	
Jobs |
---- |
To retrieve an Archive or Inventory, a job must be initiated. |	
Retrievals are queued. |
When the job terminates, download of output is ready. |
Can configure SNS notifications to be informed when	a job is finished and output is ready for download. |
	
Vault Locks	|
----------- |
Can lock a vault policy and it becomes immutable. |
	
Data Retrival Policies |
---------------------- |
For Standard Retrieval option only |
Set retrieval limits to: |	
   |	- Free Tier only |
   |	- Max retrieval rate (bytes per hour) |
   |	- No retrieval limit |
	
Pricing	|
------- |
Storage	|
Data Retrievals	|
   |	- Expedited (most expensive)
   |	- Standard
   |	- Bulk (cheapest)
Upload Request |
Data transfer OUT to other regions |
Data transfer OUT to the internet |
	
Amazon Glacier Select |
--------------------- |
Allows  queries to Archives stored in Glacier to use for analytics.	|