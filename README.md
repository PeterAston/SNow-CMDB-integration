# SNow-CMDB-integration
Populate/maintain SNow CMDB with external data sources


Populate/maintain CMDB with data from SCOM, SolarWinds, PowerShell, Excel, Trend, VMWare etc

SNow Import Set API - https://docs.servicenow.com/bundle/rome-application-development/page/integrate/inbound-rest/concept/c_ImportSetAPI.html
Tie SNow sysID to SCOM's object ID, presumably other systems have unique oids as well
Use a REST API POST to push data from source into SNow CMDB?
Need to define what information is required and how it maps to fields in SNow. 
Needs to include child objects that are populated or relevant - e.g. if parent = server, then also include disks, nic, OS etc
Needs to include relationships between objects, e.g. if Service is mapped in SquaredUp, then it exists as an 'Enterprise Application' within SCOM, and those relationships (Server talks to server on port XX, SNAT, SolarWinds hardware etc) are included.
Needs to be on a regular sync
Two way would be good so that support information could be added as custom fields in SCOM and visible in SquaredUp

How do we get the data from the source
How do we format that data to ServiceNow's requirements

There are a few options available for populating ServiceNow CMDB from an external source for free:

Discovery: ServiceNow provides a free version of Discovery for customers with a ServiceNow instance. This version allows you to discover up to 128 IP addresses and populate the CMDB with the discovered data. You can enable Discovery in your ServiceNow instance and configure it to discover the devices and applications in your IT environment.

Import Sets: ServiceNow allows you to create and run Import Sets for free. You can use this feature to import data from external sources into the CMDB. You can create an import set to map the fields in your source data to the corresponding CMDB fields, and then use the import set to populate the CMDB.

API: ServiceNow provides a REST API that you can use to programmatically create, read, update, and delete CMDB records. You can use the API to integrate with any system that can send or receive HTTP requests. There are no additional costs to use the ServiceNow API.
