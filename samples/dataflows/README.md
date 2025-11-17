# Data Flow Samples

This directory contains Azure Data Factory mapping data flow samples for complex data transformations.

## Available Samples

### 1. Data Cleansing Flow
**File**: `data-cleansing-flow.json`

Data flow that cleanses and validates input data.

**Transformations**:
- Remove null values
- Trim whitespace
- Validate data formats
- Filter invalid records

**Use Case**: Data quality improvement

## What are Mapping Data Flows?

Mapping data flows are visually designed data transformations in Azure Data Factory. They allow you to:

- Transform data at scale without writing code
- Use a visual interface to design transformations
- Execute transformations on Azure Databricks Spark clusters
- Handle complex data transformation logic

## Common Transformations

### Source
Defines the input data source for the data flow.

### Select
Choose specific columns and rename them.

### Filter
Apply conditions to filter rows.

### Derived Column
Create new columns or modify existing ones using expressions.

### Aggregate
Group data and perform aggregations (SUM, AVG, COUNT, etc.).

### Join
Combine data from multiple sources.

### Conditional Split
Route rows to different streams based on conditions.

### Sink
Defines the output destination for transformed data.

## Data Flow Expressions

Data flows use expression language for transformations:

```
// String operations
upper(CustomerName)
trim(Address)
concat(FirstName, ' ', LastName)

// Date operations
currentDate()
addDays(OrderDate, 7)
year(TransactionDate)

// Conditional logic
iif(Amount > 1000, 'High', 'Low')

// Null handling
coalesce(Phone, 'N/A')
isNull(Email)
```

## Debug Mode

Use Debug mode to:
- Test data flows with sample data
- Preview transformation results
- Validate logic before deployment
- Troubleshoot issues

## Performance Tips

1. **Use appropriate cluster size** for your data volume
2. **Enable compute optimizations** for large datasets
3. **Partition data** for parallel processing
4. **Use broadcast joins** for small lookup tables
5. **Enable data flow staging** for better performance

## How to Use

1. Create a data flow in your ADF instance
2. Import the JSON definition
3. Configure source and sink datasets
4. Enable debug mode
5. Test with sample data
6. Add to a pipeline for orchestration
