# Real_Time_Retail_Streaming_Pipeline
***
## Project Overview
This project is an overview of an real-time retail streaming pipeline using Apache Kafka with separate Orders and Payments topics. Implemented stream-stream joins using Kafka Streams to generate enriched order events. Configured Kafka Connect MongoDB Sink to persist processed data into MongoDB Atlas, enabling real-time business dashboards and revenue analytics.
***

## Architectural Diagram
![Architecture Design](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/d43e21b4fde3abe4b304dd03ee2a478dcf1f44d9/Images/Flow_Diagram.png)
***
## Key Steps
### 1. Create required Topics and Stream 
- Topics: orders,payment 
- Stream: retail_orders_raw_stream,retail_payments_raw_stream,retail_orders_payments_raw_joined as part of setup process.
    ![orders_topic](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b63a76ddf3b89f6e60f713d8addd1824d17017f0/Images/orders_raw_topic.png)
    ![payment_topic](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b63a76ddf3b89f6e60f713d8addd1824d17017f0/Images/payments_raw_topic.png)
    ![Streams](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b63a76ddf3b89f6e60f713d8addd1824d17017f0/Images/streams.png)

***

### 2. Create Cluster and Collection in MongoDB 
- Create cluster,required Database and collection in MongoDB which acts as a sink in this pipeline.
   ![MongoDB Cluster,Collection](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/7d7ff311e0baee2b946b5a48a841dcd198c98185/Images/mongodb_cluster_db.png)

  ***

### 3. Create MongoDB Sink Connector in Kafka
   ![MongoDB Sink_Connector](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/7d7ff311e0baee2b946b5a48a841dcd198c98185/Images/mongodb_sink_connector.png)


### 4. Mock Data Generation using Producer Code
- Generate mock Data for the customers based on orders and payments.
  - Producer:
  ![Codebuild](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b1b78099d9adbed2265b82e9ad97a13c01e89daf/Images/producer.png)
  ***


### 5. Validate the data
- Validate the data across topics and streams
- Joined data of customer and producer will be a part of retail_orders_payments_raw_joined stream in retail_transformed_data topic
  ![Data in retail_orders_payments_raw_joined Stream](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/7d7ff311e0baee2b946b5a48a841dcd198c98185/Images/streams2.png)

- Once the data is produced into retail_transformed_data topic,through the MongoDB Sink Connector(which works as consumer here) data will be pushed to MongoDB
 ![Data in MongoDB](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/7d7ff311e0baee2b946b5a48a841dcd198c98185/Images/mongodb_collection.png)

### 6. Create MongoDB Charts:
- To visualize the data we create charts in MongoDB
  ![Sample Charts](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/7d7ff311e0baee2b946b5a48a841dcd198c98185/Images/Mongo_DB_Charts.png)
