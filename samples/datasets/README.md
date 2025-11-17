# Dataset Samples

This directory contains Azure Data Factory dataset samples for various data formats and sources.

## Available Samples

### 1. Binary Blob Dataset
**File**: `binary-blob-dataset.json`

Dataset for binary file handling in Azure Blob Storage.

**Format**: Binary (any file type)

**Use Case**: Copying files as-is without schema interpretation

### 2. CSV Dataset
**File**: `csv-blob-dataset.json`

Dataset for CSV files in Azure Blob Storage.

**Format**: Delimited Text (CSV)

**Use Case**: Structured data in CSV format

### 3. Parquet Dataset
**File**: `parquet-dataset.json`

Dataset for Parquet files.

**Format**: Parquet

**Use Case**: Big data scenarios with columnar storage

### 4. SQL Table Dataset
**File**: `sql-table-dataset.json`

Dataset for Azure SQL Database tables.

**Format**: SQL Table

**Use Case**: Relational database operations

## Dataset Properties

### Common Properties

All datasets include:
- **Linked service reference**: Connection to data source
- **Parameters**: For dynamic dataset behavior
- **Schema**: Column definitions (optional)
- **Structure**: Data type mappings

### Parameterization

Datasets support parameters for dynamic behavior:

```json
"parameters": {
  "containerName": {
    "type": "string"
  },
  "folderPath": {
    "type": "string"
  },
  "fileName": {
    "type": "string"
  }
}
```

### Example Usage in Pipeline

```json
"inputs": [
  {
    "referenceName": "CsvDataset",
    "type": "DatasetReference",
    "parameters": {
      "containerName": "input",
      "folderPath": "data/2024",
      "fileName": "sales.csv"
    }
  }
]
```

## Schema Definitions

### Explicit Schema

```json
"schema": [
  {
    "name": "CustomerID",
    "type": "String"
  },
  {
    "name": "OrderDate",
    "type": "DateTime"
  },
  {
    "name": "Amount",
    "type": "Decimal"
  }
]
```

### Schema Import

You can also import schema from the data source using the Azure Data Factory UI.

## Best Practices

1. **Use parameterization** for reusable datasets
2. **Define schema** explicitly when possible for validation
3. **Use appropriate file formats** for your use case
4. **Configure compression** for large files
5. **Set proper encoding** for text files
