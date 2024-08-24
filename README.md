![image](https://github.com/user-attachments/assets/bfb08cbe-a6d1-4f2a-b4ec-6a30b8ee348e)

A **chatbot** is a type of software that interacts with users through automated conversations on messaging platforms like Telegram. **Telegram**, a freeware and mostly open-source instant messaging platform, provides an ideal environment for developing projects that involve interaction with large volumes of user-generated data.

The objective of this project is to **build a data pipeline** that can ingest, process, store, and expose messages from a Telegram group, enabling data professionals to conduct in-depth analyses of group interactions. The proposed architecture is divided into two complementary parts: the transactional layer, where messages are generated and collected on Telegram, and the analytical layer, where the data is processed and analyzed on Amazon Web Services (AWS).

This activity was a challenge proposed by EBAC as the Final Project for the Big Data and Cloud Computing Module.

**Tools:**
- AWS (Lambda, S3, Athena, Api Gateway, Event Bridge)
- Python
- SQL
  
**Step by step**
1. Set up telegram:
* Create a new bot using BotFather.
* Start a new group and add your bot as a member.
* Promote the bot to administrator within the group.
* Disable the setting that allows the bot to be added to other groups.
* Use the Telegram Bot API to retrieve and process these messages.
2. Pipeline
  
  2.1. Data Ingestion
* Creating buckets to save raw data.
* Using AWS Lambda Function to receive messages and storage in JSON format at raw data bucker.
* Create an API with AWS Api Gateway to receives messages captured by Telegran Bot, sent via webhook, and trigger an AWS Lambda function, passing the message content in its event parameter.
  
  2.2. ETL
* Second AWS Lambda with function responsible for processing and data wrangling the messages captured by the Telegram bot.
* Rule in AWS EventBridge to execute the AWS Lambda function every day.
3. Data analysis using AWS Athena with SQL querys

