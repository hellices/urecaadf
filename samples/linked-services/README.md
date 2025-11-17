# Linked Services Samples

This directory contains Azure Data Factory linked service samples for connecting to various data sources and destinations.

## Available Samples

### 1. Azure Blob Storage
**File**: `azure-blob-storage.json`

Linked service configuration for Azure Blob Storage.

**Connection Type**: Storage Account Key

**Use Case**: Connect to Azure Blob Storage for data movement

### 2. Azure SQL Database
**File**: `azure-sql-database.json`

Linked service configuration for Azure SQL Database.

**Authentication**: SQL Authentication

**Use Case**: Connect to Azure SQL Database for data read/write operations

### 3. Azure Data Lake Storage Gen2
**File**: `azure-data-lake-gen2.json`

Linked service configuration for Azure Data Lake Storage Gen2.

**Authentication**: Service Principal

**Use Case**: Connect to ADLS Gen2 for big data scenarios

## Configuration Notes

### Security Best Practices

1. **Never hardcode credentials** in linked service definitions
2. **Use Azure Key Vault** to store connection strings and keys
3. **Use Managed Identity** when possible for Azure services
4. **Parameterize** connection properties for flexibility

### Example: Using Key Vault References

```json
"connectionString": {
  "type": "AzureKeyVaultSecret",
  "store": {
    "referenceName": "AzureKeyVault",
    "type": "LinkedServiceReference"
  },
  "secretName": "sql-connection-string"
}
```

### Example: Using Parameters

```json
"typeProperties": {
  "connectionString": {
    "value": "@{linkedService().serverName}",
    "type": "Expression"
  }
}
```

## How to Deploy

### Using Azure Portal
1. Navigate to your Data Factory instance
2. Go to "Manage" → "Linked services"
3. Click "+ New"
4. Select the appropriate connector type
5. Import or configure using the sample JSON
6. Test the connection
7. Save

### Using Azure CLI
```bash
az datafactory linked-service create \
  --resource-group <resource-group> \
  --factory-name <factory-name> \
  --name <linked-service-name> \
  --properties @linked-service.json
```

## Common Parameters

- `accountName`: Storage account name
- `serverName`: Database server name
- `databaseName`: Database name
- `userName`: Authentication username
- `endpoint`: Service endpoint URL
