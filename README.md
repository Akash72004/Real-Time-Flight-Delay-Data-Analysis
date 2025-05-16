# Real-Time-Flight-Delay-Data-Analysis

## 1. INTRODUCTION
Flight delays are a significant issue in the aviation industry, impacting passengers, airlines, and
airport operations. Analyzing delay patterns and understanding the contributing factors is
essential to optimize airport management, improve customer satisfaction, and reduce economic
losses. This project focuses on analyzing flight delay data through a comprehensive data
pipeline. By leveraging Apache Kafka and Apache Spark for data ingestion and preprocessing,
AWS S3 and Redshift for data storage, and Tableau for visualization, we gain insights into
delay trends and patterns. The aim of this project is to build an efficient data pipeline to extract,
transform, load, and analyze large-scale flight delay data.

## 2. DATA DESCRIPTION AND ANALYSIS
United States Department of Transportation The U.S. Department of Transportation's (DOT)
Bureau of Transportation Statistics (BTS) tracks the on-time performance of domestic flights
operated by large air carriers. Summary information on the number of on-time, delayed, canceled
and diverted flights appears in DOT's monthly Air Travel Consumer Report, published about 30
days after the month's end, as well as in summary tables posted on this website. BTS began
collecting details on the causes of flight delays in June 2003.
Following are the columns:
year, month, carrier, carrier_name, airport, airport_name, arrivals, arrival_delay,
arrival_delay_by_15min, total_arrival_delays, weather_delay, carrier_delay, arr_divert

## 3. DESIGN OF DATA PIPELINE

### 3.1. Data Ingestion
The pipeline begins with data ingestion using Apache Kafka, which streams real-time data
from flight delay APIs. Kafka's robust messaging system ensures data is ingested reliably.

### 3.2. Data Preprocessing
Data preprocessing is performed using Apache Spark, which involves reading and cleaning
streaming flight delay data by dropping rows with excessive missing values, filling remaining
nulls, renaming columns for clarity, and capping delay percentages at 100%.

### 3.3 Data Storage
The preprocessed data is stored in an AWS S3 bucket for persistence. AWS Glue is then used
to crawl through the data in our AWS S3 bucket and use AWS Glue ETL job to perform
operations, cataloging the data to be queried in Redshift.

### 3.4 Data Warehouse (Redshift)
Amazon Redshift serves as the data warehouse, where the data is loaded and structured for
analytical processing. Redshift allows efficient querying of large datasets and is well-integrated
with visualization tools like Tableau.

### 3.5 Data Visualization
Tableau is used to create dashboards and interactive visualizations, enabling easy exploration
of flight delay patterns. The visualizations include state-wise maps, city-wise delay trends, and
carrier-wise delay distributions, helping to identify patterns and outliers.

## 4. RESULT ANALYSIS
![Image](https://github.com/user-attachments/assets/68b46f73-0bbb-45a3-acb3-6e344b762bf3)


