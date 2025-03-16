##Logstash Solution Explanation

#1. Data Ingestion

The logs are read from input.log using the file input plugin.

The start_position is set to "beginning" to ensure all logs are processed.

The codec is set to plain (charset => "UTF-8") to handle text data properly.


#2. Data Parsing & Normalization

The Grok filter is used to extract structured data from log messages.

It captures fields such as number, timestamp, and message content.

The mutate filter converts the severity field from string to integer for consistency.

Based on severity values:

1 is labeled "High"

2 is labeled "Medium"

3 or 4 is labeled "Low"

Any other value is labeled "Unknown"


#3. Output Processing

The processed logs are printed to the console using the rubydebug codec for debugging.

The transformed logs are stored in JSON format at:

C:/Users/<yourpath>/logstash-8.17.3/logs/output.json


#4. Sample Input & Output

Sample Input (input.log)

Extracted & Transformed Output (output.json)

