# Real-time Weather Data ETL Pipeline with Apache Airflow and AWS

## Project Overview

This project demonstrates the implementation of an automated ETL (Extract, Transform, Load) pipeline for real-time weather data using Apache Airflow and AWS. The pipeline extracts current weather data from the OpenWeatherMap API, transforms it, and loads it into an AWS S3 bucket.

## Features

- Automated data extraction from OpenWeatherMap API
- Data transformation using Python
- Data loading into AWS S3
- Workflow orchestration and scheduling with Apache Airflow
- Error handling and monitoring

## Tech Stack

- Apache Airflow
- Python
- AWS S3
- REST APIs
- Docker
- JSON/CSV

## Project Structure
![etl img](image.png)


## Setup and Installation

1. Clone this repository
2. Install the required dependencies:
    * sudo apt update
    * sudo apt install python3-pip
    * sudo apt install python3.10-venv
    * python3 -m venv airflow_venv
    * sudo pip install pandas
    * sudo pip install s3fs
    * sudo pip install apache-airflow
    * airflow standalone
    * sudo apt  install awscli
    * aws configure
    * aws sts get-session-token
3. Set up Apache Airflow
4. Configure AWS credentials
5. Set up the OpenWeatherMap API connection in Airflow

## Usage

1. Start the Airflow webserver and scheduler
2. Access the Airflow UI and enable the `weather_dag`
3. The DAG will run daily, extracting weather data for Portland, transforming it, and loading it into the specified S3 bucket

## DAG Structure

1. `is_weather_api_ready`: HttpSensor to check API availability
2. `extract_weather_data`: SimpleHttpOperator to fetch data from the API
3. `transform_load_weather_data`: PythonOperator to transform data and load it to S3
