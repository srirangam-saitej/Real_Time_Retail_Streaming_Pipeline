# Real_Time_Retail_Streaming_Pipeline
***
## Project Overview
This project is an overview of an real-time retail streaming pipeline using Apache Kafka with separate Orders and Payments topics. Implemented stream-stream joins using Kafka Streams to generate enriched order events. Configured Kafka Connect MongoDB Sink to persist processed data into MongoDB Atlas, enabling real-time business dashboards and revenue analytics.
***

## Architectural Diagram
![Architecture Design](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/d43e21b4fde3abe4b304dd03ee2a478dcf1f44d9/Images/Flow_Diagram.png)

***
## Key Steps
Create required Topics and Stream

- orders,payment topics and retail_orders_raw_stream,retail_payments_raw_stream,retail_orders_payments_raw_joined as part of  setup process.

  ![orders_topic](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b63a76ddf3b89f6e60f713d8addd1824d17017f0/Images/orders_raw_topic.png)
  ![payment_topic](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b63a76ddf3b89f6e60f713d8addd1824d17017f0/Images/payments_raw_topic.png)
  ![Streams](https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b63a76ddf3b89f6e60f713d8addd1824d17017f0/Images/streams.png)
  !(https://github.com/srirangam-saitej/Real_Time_Retail_Streaming_Pipeline/blob/b63a76ddf3b89f6e60f713d8addd1824d17017f0/Images/streams2.png)
