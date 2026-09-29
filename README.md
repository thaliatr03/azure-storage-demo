# azure-storage-demo

## Overview

This project demonstrates how to:

1. Store JSON files in Azure Blob Storage.
2. Read JSON files from an Azure Storage Account using Python.
3. Transform time-series market data.
4. Generate benchmark-based date features.
5. Save transformed data back to Azure Blob Storage.
6. Use GitHub Copilot in VS Code to assist with code generation.

The exercise simulates a workflow similar to working with market data stored in Azure Storage.

---

## Sample Data

Input JSON files contain records with the following structure:

```json
{
  "Date": "2024-01-01",
  "OpenPrice": 110.56,
  "ClosePrice": 107.71,
  "HighPrice": 111.11,
  "LowPrice": 107.26,
  "VolumeOfTrade": 486123
}
```

### Fields

- Date
- OpenPrice
- ClosePrice
- HighPrice
- LowPrice
- VolumeOfTrade

---

## Objective

Read time-series data from Azure Blob Storage and create additional date-derived features using the benchmark date:

```text
1900-01-01 00:00:00
```

### Output Columns

| Column |
|----------|
| DaysFromBenchmark |
| WorkingDaysFromBenchmark |
| WeeksFromBenchmark |
| MonthsFromBenchmark |
| DayOfWeek |
| DayOfMonth |
| WorkingDayOfMonth |
| OpenPrice |
| ClosePrice |
| HighPrice |
| LowPrice |
| VolumeOfTrade |

---

## Project Structure

```text
azure-storage-demo/
│
├── data/
│   ├── fictitious_timeseries_1.json
│   ├── fictitious_timeseries_2.json
│   └── fictitious_timeseries_3.json
│
├── transform_timeseries.py
├── requirements.txt
└── README.md
```

---

## Prerequisites

### Software

- Visual Studio Code
- Git
- Python 3.10+
- GitHub Copilot Extension

### Azure Resources

- Azure Subscription
- Azure Storage Account
- Blob Container

---

## Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/azure-storage-demo.git
```

Navigate into the project:

```bash
cd azure-storage-demo
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Required Packages

Create a file called `requirements.txt`

```text
azure-storage-blob
pandas
numpy
```

Install:

```bash
pip install -r requirements.txt
```

---

## Azure Storage Setup

1. Create an Azure Storage Account.
2. Create a Blob Container named:

```text
market-data
```

3. Upload the sample JSON files.
4. Obtain the Storage Account Connection String.

Azure Portal:

```text
Storage Account
    -> Access Keys
    -> Connection String
```

---

## Example Workflow

```text
JSON File
    ↓
Azure Blob Storage
    ↓
Python Script
    ↓
Feature Engineering
    ↓
New JSON File
    ↓
Azure Blob Storage
```

---

## GitHub Copilot Prompt

Use the following prompt in VS Code Copilot Chat:

```text
Create a Python script that reads a JSON file from Azure Blob Storage.

Input fields:
Date
OpenPrice
ClosePrice
HighPrice
LowPrice
VolumeOfTrade

Create:
DaysFromBenchmark
WorkingDaysFromBenchmark
WeeksFromBenchmark
MonthsFromBenchmark
DayOfWeek
DayOfMonth
WorkingDayOfMonth

Benchmark:
1900-01-01

Save the transformed output back to Azure Blob Storage.
```

---

## Expected Outcome

The solution should:

- Read market data from Azure Blob Storage.
- Generate benchmark date metrics.
- Save transformed records to Azure Storage.
- Demonstrate Azure Storage integration using Python.
- Demonstrate GitHub Copilot-assisted development in VS Code.


