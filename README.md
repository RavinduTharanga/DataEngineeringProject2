# Reddit Data Pipeline

This project provides an end-to-end data pipeline for extracting, transforming, and loading (ETL) Reddit data into an Amazon Redshift data warehouse. By leveraging Apache Airflow, Celery, PostgreSQL, Amazon S3, AWS Glue, Amazon Athena, and Amazon Redshift, this pipeline ensures efficient data processing and analytics.

## Architecture
![RedditDataEngineering.png](RedditDataEngineering.png)

## Features
- **Automated ETL**: Seamlessly extract, transform, and load Reddit data.
- **Scalable Storage**: Use Amazon S3 for raw data storage.
- **Efficient Transformation**: AWS Glue and Athena for structured transformations.
- **Robust Orchestration**: Apache Airflow for workflow management.
- **Powerful Analytics**: Amazon Redshift for querying and Power BI for visualization.

## Pipeline Workflow
1. **Data Extraction**: Fetches Reddit data via API.
2. **Raw Data Storage**: Saves extracted data into Amazon S3.
3. **Metadata Management**: Uses PostgreSQL for tracking processes.
4. **Data Transformation**: AWS Glue and Athena clean and format the data.
5. **Data Loading**: Transfers transformed data into Amazon Redshift.
6. **Visualization**: Power BI provides insights into processed data.

## Technologies Used
- **Apache Airflow & Celery**: Workflow scheduling and task management.
- **PostgreSQL**: Metadata storage.
- **Amazon S3**: Cloud storage for raw data.
- **AWS Glue**: ETL and schema cataloging.
- **Amazon Athena**: SQL-based querying and transformation.
- **Amazon Redshift**: Data warehousing for analytics.
- **Power BI**: Business intelligence and data visualization.

## Installation & Setup
### Prerequisites
Ensure you have the following:
- **AWS Account** with permissions for S3, Glue, Athena, and Redshift.
- **Reddit API Credentials** to access Reddit data.
- **Docker Installed** for containerized services.
- **Python 3.9+** for running scripts.

### Steps to Setup
1. Clone this repository:
   ```sh
   git clone https://github.com/airscholar/RedditDataEngineering.git
   cd RedditDataEngineering
   ```
2. Create and activate a virtual environment:
   ```sh
   python3 -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate  # Windows
   ```
3. Install required dependencies:
   ```sh
   pip install -r requirements.txt
   ```
4. Configure settings:
   ```sh
   mv config/config.conf.example config/config.conf
   ```
   Add your credentials and configuration details in `config.conf`.
5. Start Docker containers:
   ```sh
   docker-compose up -d
   ```
6. Access the Airflow web UI:
   ```sh
   open http://localhost:8080
   ```
   (Or manually navigate to `http://localhost:8080` in your browser.)

## Usage
- **Run the ETL Pipeline**: Trigger Airflow DAGs to extract and process Reddit data.
- **Monitor Workflow**: Use the Airflow UI to track tasks and logs.
- **Query Transformed Data**: Access Athena and Redshift for structured queries.
- **Visualize Insights**: Load Redshift data into Power BI for analysis.



