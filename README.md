# Amazon Prime Day Sales Data Projection (RealTime Data Streaming)
**Overview**

This project demonstrates a robust real-time data engineering pipeline built with AWS services and Python scripts to ingest, process, and analyze streaming sales data. The pipeline efficiently captures, transforms, and stores data, enabling real-time analytics and insights.

**Architecture**

![Architecture](https://github.com/user-attachments/assets/679249f1-887e-4ece-a858-4899b6aa4a02)

The architecture of the pipeline involves the following components:

**Source Data Generation:** Python scripts simulate real-time sales data.

**Data Ingestion:** Boto3 library is used to ingest the generated data into DynamoDB.

**Change Data Capture (CDC):** DynamoDB Streams track changes for real-time processing.

**Streaming Data Processing:** EventBridge Pipe sends the DynamoDB stream records to a Kinesis stream.

**Data Accumulation:** Kinesis Firehose accumulates the streaming records for a certain period before processing.

**Data Transformation:** Lambda functions perform transformations on the accumulated records before dumping them into S3 in JSON format.

**Metadata Preparation:** Transformed data is stored in S3, with metadata managed by AWS Glue, allowing for querying via Athena.

**Setup**

**1.AWS Configuration:** Set up AWS credentials for accessing DynamoDB and related services.

**2.Deploy Scripts:** Run Python scripts to generate and ingest mock sales data.

**3.Configure Streams & Processing:** Set up DynamoDB Streams, EventBridge, Kinesis, and Lambda for real-time data processing.

**4.Data Storage:** Configure Kinesis Firehose and S3 for data storage.

**5.Metadata Management:** Use Glue Crawlers to enable Athena queries on stored data.

**Results**
Once deployed, this pipeline continuously processes and stores real-time sales data, allowing for immediate analysis and insight generation through Athena queries.

