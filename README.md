# NBA DATA LAKE
The NBA Data Lake is an end-to-end data analytics pipeline designed to fetch, process, store, and transform NBA player data for analytics and visualization. This README provides an overview of the project structure, components, and instructions to set up and use the system.

## Project Overview

- The NBA Data Lake performs the following tasks:

- Fetches raw NBA data from an external API.

- Stores the raw data in an S3 bucket.

- Processes and cleans the data using an AWS Glue ETL job.

- Queries the processed data using Amazon Athena.

- Visualizes the data in Amazon QuickSight.


## Architecture

The architecture comprises the following AWS components:

- Amazon S3: Stores raw and processed data.

- AWS Glue:

  - Crawler: Catalogs the data and creates a schema in the Glue Data Catalog.

  - ETL Job: Transforms raw data into a structured format.

- Amazon Athena: Queries the processed data for analytics.

- Amazon QuickSight: Provides data visualization and reporting.

- AWS IAM: Manages permissions for resources and services.

[Architecture](./media/nba_data_lake_architecture.jpeg)

## Project Structure
```markdown
    nba-data-lake/  
    ├── media/                      # media file
    |  
    ├── src/  
    │   └── nba_data_lake.py        # python script 
    │           
    ├── .env.example                # configurable env variables
    ├── .gitignore                  # Ignored files  
    ├── manifest.json               # manifest file for quicksight 
    ├── README.md                   # Project documentation 
    └── requirements.txt            # python dependencies    
```

## Getting Started

- Prerequisites

 - An AWS account with access to the following services: S3, Glue, Athena, and QuickSight.
 - AWS CLI installed and configured.
 - API KEY from soortsdata.io

## Steps

1. Clone the Repository:
```bash
    git clone https://github.com/oyogbeche/nba_data_lake.git
    cd nba_data_lake
```

2. Configure the `.env` using `.env.example`

3. Create and activate venv
```bash
    python -m venv myenv
    myenv\Scripts\Activate
```
4. Install dependencies
```bash
    pip install -r requirements.txt
```
5. Configure aws credentials
```bash
    aws configure
```
6. Run the application
```bash
    python src/nba_data_lake.py
```