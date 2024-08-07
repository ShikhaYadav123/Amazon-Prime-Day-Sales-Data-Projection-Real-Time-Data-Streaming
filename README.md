# Amazon Prime Day Sales Data Projection (RealTime Data Streaming)
**Overview**

This project implements a real-time data engineering pipeline for ingesting, processing, and analyzing streaming data. The pipeline utilizes various AWS services and Python scripts to achieve end-to-end data processing and analysis capabilities.

**Architecture**

![Architecture](https://github.com/user-attachments/assets/679249f1-887e-4ece-a858-4899b6aa4a02)

The architecture of the pipeline involves the following components:

**Source Data Generation:** Python mock scripts generate real-time data as the source.

**Data Ingestion:** Boto3 library is used to ingest the generated data into DynamoDB.

**Change Data Capture (CDC):** DynamoDB Streams capture any changes in the DynamoDB table.

**Streaming Data Processing:** EventBridge Pipe sends the DynamoDB stream records to a Kinesis stream.

**Data Accumulation:** Kinesis Firehose accumulates the streaming records for a certain period before processing.

**Data Transformation:** Lambda functions perform transformations on the accumulated records before dumping them into S3 in JSON format.

**Metadata Preparation:** A Glue Crawler crawls the S3 bucket to prepare metadata, enabling querying of the data using Athena.

**Setup**
To set up the project, follow these steps:

1.Configure AWS credentials and permissions for the Boto3 library to access DynamoDB AWS services.

2.Deploy the Python mock scripts to generate source data.

3.Set up DynamoDB tables and streams for data ingestion and CDC.

4.Create EventBridge rules and Kinesis streams for streaming data processing.

5.Configure Kinesis Firehose delivery streams and Lambda functions for data transformation.

6.Set up a Glue Crawler to crawl the S3 bucket and prepare metadata for Athena.

**Usage**
Once the project is set up, the pipeline will automatically ingest, process, and analyze streaming data in real-time. Data engineers and analysts can query the data using Athena to derive insights and make near real time data-driven decisions.


