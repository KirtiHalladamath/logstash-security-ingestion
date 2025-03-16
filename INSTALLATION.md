# Logstash Installation Guide
Follow these steps to install Logstash on Windows.

## Step 1: Download Logstash
Download Logstash from [Elastic's website](https://www.elastic.co/downloads/logstash).

## Step 2: Extract Logstash
Extract the ZIP file to C:\logstash (We have extracted in C:\users\halla<user folder>\logstash).

## Step 3: Verify Installation
Open PowerShell, navigate to the folder, and check the version:
```sh
cd C:\logstash
.\bin\logstash --version
