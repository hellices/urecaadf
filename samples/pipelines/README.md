# Pipeline Samples

This directory contains Azure Data Factory pipeline samples demonstrating various data orchestration patterns.

## Available Samples

### 1. Copy Data Pipeline
**File**: `copy-blob-to-blob.json`

A basic pipeline that copies data from one Azure Blob Storage container to another.

**Use Case**: Simple data movement between storage locations

**Key Features**:
- Copy Activity
- Parameterized source and destination
- Error handling

### 2. Incremental Load Pipeline
**File**: `incremental-load.json`

Pipeline that performs incremental data loading based on a watermark column.

**Use Case**: Loading only new or updated records

**Key Features**:
- Lookup Activity
- Watermark pattern
- Conditional execution

## How to Use

1. Review the pipeline JSON file
2. Update the linked service references to match your ADF instance
3. Configure parameters with your specific values
4. Import into Azure Data Factory
5. Test with sample data

## Common Parameters

Most pipelines support the following parameters:
- `sourcePath`: Source data location
- `destinationPath`: Destination data location
- `containerName`: Storage container name
- `folderPath`: Folder path within container
