# Export Power BI activity events associated with a specific workspace

The script will prompt for credentials using a browser. Many other authentication methods are supported by the DefaultAzureCredential class. Refer to the Azure Identity [documentation](https://github.com/Azure/azure-sdk-for-python/tree/main/sdk/identity/azure-identity#defaultazurecredential)

Install the Azure Identity package:
```
pip install azure-identity
```

Run the export:
```
python workspace-activity.py <Workspace GUID>
```
The script will create a csv file in the current folder.

## Modify initial variable values (optional)

```
batch_hours = 24
```
Number of hours to include in a single batch. For larger tenants where a single request may result is a timeout, reducing this number to 6 or even 1 may be necessary. A smaller number will result in the script taking longer to complete.

```
activity_log_days = 30
```
Total numner of days to include in the export starting from today and going backwards. 30 is the maximum number supported by Power BI.
