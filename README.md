## Geo-Data Ingestion for Tables and Attack Maps

Azure does not provide geolocation for IP addresses. To determine the city/country of the IP address and plot it on a map, I uploaded geo-data files to correlate IP address and its block with a longitude and latitude to determine the city/country to plot it on a map.

## Upload Geo-Data Files in Container & Generate SAS URL
I encountered a situation where the files were too large to upload directly to the Watchlist. To address this, I uploaded the files into a container in Storage and created SAS URLs. This allowed me to share the files securely and efficiently.
![geo-file-upload](https://github.com/spencermoy/azure-soc-honeynet/assets/137566643/6c67a1bc-5982-4c9e-a172-666c7b4ea972)<br>
![sas-right-click](https://github.com/spencermoy/azure-soc-honeynet/assets/137566643/f25a0db7-753c-4547-963a-778d62242ba4)<br>
![generate-sas](https://github.com/spencermoy/azure-soc-honeynet/assets/137566643/e18cefab-661c-4661-a449-14ae5f882569)<br>

## Create Watchlist with SAS URL
I connected Logistic Analytics Workspace to Microsoft Sentinel and created a Watchlist for each geo-data file. 
![create_watchlist](https://github.com/spencermoy/azure-soc-honeynet/assets/137566643/c2974cac-4f0f-4f14-a505-0659c703f03a)<br>
I then let it ingest the data. 
Microsoft Sentinel Watchlist can be used to import a list of details and transform them into a log format stored in Log Analytics Workspace for use within Sentinel. It also allows me to upload workbooks to plot attack maps.
![watchlist-ingesting-status](https://github.com/spencermoy/azure-soc-honeynet/assets/137566643/a9de23df-48a8-4e56-ac3b-a4be5b503603)<br>



