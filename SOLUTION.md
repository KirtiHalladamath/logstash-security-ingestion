# Logstash Solution Explanation

## Data Ingestion
- Security logs are read from logfile.log using the file input plugin.
- The logs are parsed using the grok filter.

## Data Normalization
- grok extracts fields like description, hostname, source_ip, and severity.
- translate converts severity numbers into "High", "Medium", or "Low".

## Output
- The processed data is output as JSON.
- As shown in logstash_output.png
