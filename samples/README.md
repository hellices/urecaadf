# Azure Data Factory Samples

Welcome to the Azure Data Factory (ADF) samples repository! This collection provides practical examples and templates for building data integration solutions using Azure Data Factory.

## 📋 Table of Contents

- [Overview](#overview)
- [Sample Categories](#sample-categories)
- [Getting Started](#getting-started)
- [Sample Structure](#sample-structure)
- [Prerequisites](#prerequisites)
- [How to Use](#how-to-use)
- [Contributing](#contributing)

## 🎯 Overview

Azure Data Factory is a cloud-based data integration service that allows you to create data-driven workflows for orchestrating data movement and transforming data at scale. These samples demonstrate common patterns and best practices for:

- Data ingestion from various sources
- Data transformation and processing
- Orchestration of complex workflows
- Integration with Azure services
- Monitoring and error handling

## 📁 Sample Categories

### 1. [Pipelines](./pipelines/)
Example pipelines demonstrating various data movement and transformation scenarios:
- Copy data between storage accounts
- Incremental data loading
- Parameterized pipelines
- Pipeline orchestration patterns

### 2. [Linked Services](./linked-services/)
Connection configurations for various data sources and destinations:
- Azure Blob Storage
- Azure SQL Database
- Azure Data Lake Storage Gen2
- REST API endpoints
- On-premises data sources

### 3. [Datasets](./datasets/)
Dataset definitions for different data formats and sources:
- CSV files
- Parquet files
- JSON documents
- Database tables
- Dynamic datasets with parameters

### 4. [Data Flows](./dataflows/)
Mapping data flows for complex transformations:
- Data cleansing and validation
- Aggregations and joins
- Conditional splits
- Schema transformations

## 🚀 Getting Started

To use these samples in your Azure Data Factory instance:

1. **Create an Azure Data Factory instance** in your Azure subscription
2. **Clone or download** this repository
3. **Navigate** to the sample you want to use
4. **Import** the JSON definition into your ADF instance using:
   - Azure Portal UI (Author & Monitor)
   - Azure PowerShell
   - Azure CLI
   - ARM templates

## 📂 Sample Structure

Each sample includes:
- **JSON definition file**: The ADF resource definition
- **README.md**: Description, purpose, and usage instructions
- **Parameters**: Configurable values for customization
- **Dependencies**: Required linked services or datasets

## ✅ Prerequisites

Before using these samples, ensure you have:

- An active Azure subscription
- Azure Data Factory instance created
- Appropriate permissions (Contributor or Data Factory Contributor role)
- Required Azure services configured (Storage Accounts, SQL Databases, etc.)
- Azure CLI or PowerShell installed (for deployment)

## 📖 How to Use

### Using Azure Portal

1. Open your Azure Data Factory instance
2. Go to "Author" tab
3. Click "+" to add new resource
4. Select "Import from template" or manually create
5. Copy the JSON content from the sample
6. Configure parameters and linked services
7. Validate and save

### Using Azure CLI

```bash
# Create a pipeline from JSON
az datafactory pipeline create \
  --resource-group <resource-group> \
  --factory-name <factory-name> \
  --name <pipeline-name> \
  --pipeline @pipeline.json
```

### Using PowerShell

```powershell
# Create a pipeline from JSON
Set-AzDataFactoryV2Pipeline `
  -ResourceGroupName <resource-group> `
  -DataFactoryName <factory-name> `
  -Name <pipeline-name> `
  -DefinitionFile "pipeline.json"
```

## 🤝 Contributing

Contributions are welcome! If you have a sample that demonstrates a useful ADF pattern:

1. Fork the repository
2. Create a feature branch
3. Add your sample with documentation
4. Submit a pull request

## 📚 Additional Resources

- [Azure Data Factory Documentation](https://docs.microsoft.com/azure/data-factory/)
- [ADF Pricing](https://azure.microsoft.com/pricing/details/data-factory/)
- [ADF Best Practices](https://docs.microsoft.com/azure/data-factory/concepts-best-practices)
- [ADF Tutorials](https://docs.microsoft.com/azure/data-factory/tutorial-copy-data-portal)

## 📄 License

These samples are provided as-is for educational and reference purposes.

---

**Note**: Remember to configure your Azure resources, update connection strings, and secure sensitive information using Azure Key Vault or ADF parameters before deploying to production environments.
