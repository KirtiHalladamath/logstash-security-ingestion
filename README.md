# Logstash Security Log Ingestion

## Description
This repository contains a Logstash pipeline configuration that ingests security log data, normalizes it, and outputs structured JSON.

## Files
- logstash.conf - Logstash configuration file
- input.log - Sample log data for ingestion
- output.json - output from Logstash
- README.md - Overview of the project
- INSTALLATION.md - Installation steps
- SOLUTION.md - Explanation of the approach
- TROUBLESHOOTING.md - Common issues and fixes

## Running the Pipeline
To test the configuration:

```sh

bin\logstash -f logstash.conf OR bin\logstash.bat -f logstash.conf


## Logstash Output Screenshot

Below is a screenshot showing Logstash successfully running

[logstash_output.png]

## Logstash Configuration test

Below is the screenshot showing tesh ran and logstash congig are correct

[logstash_test_config.png]
