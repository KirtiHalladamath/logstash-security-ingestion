# Troubleshooting & Debugging Guide for Logstash

This guide provides solutions for common Logstash issues and debugging techniques.
##1. Logstash Not Starting?  
###*Check if Java is Installed*  
- Run:
  sh
  java -version
##If missing, install OpenJDK
Check for Logstash Errors

##Run Logstash in test mode to check for syntax issues:

.\bin\logstash --config.test_and_exit -f logstash.conf

If Logstash exits with an error, check the output and fix the reported issue.


##2.Debugging Logstash Execution

##Enable Debug Mode

Run Logstash with detailed logging:

.\bin\logstash.bat --log.level debug -f logstash.conf

This will print detailed logs to help identify issues.

##3️.Logstash Not Processing Logs?

#Check If Logstash is Reading the Log File

1. Open logstash.conf and verify:

file {
  path => "C:/logstash/logfile.log"
  start_position => "beginning"
  sincedb_path => "NUL"
}

2. Ensure:

The log file exists at C:/logstash/logfile.log

New log entries are added while Logstash is running.

###Force Logstash to Re-read the File
1. Delete sincedb file (removes tracking of already read logs):

del "C:/Users/YourUsername/.sincedb*"

2. Restart Logstash:

.\bin\logstash -f logstash.conf


##4️.JSON Output Not Showing?

###Check Output Configuration

Ensure your logstash.conf output section is correct:

output {
  stdout { codec => json }
}

Run Logstash and verify JSON output appears in the console.

##5. Checking Logstash Logs for Errors

If Logstash runs as a service, check its logs:

C:\logstash\logs\logstash-plain.log

Open the log file and search for ERROR messages.

##6️.Common Errors and Fixes
Issue | Error Message | Fix
-----------------------------
Java Missing | java not found | Install open JDK
-------------------------------------------------
Syntax error in logstash.conf | Unknown setting '...' | Check logstash.conf syntax
-----------------------------------------------------------------------------------
No logs processed | No output in the console | Ensure input.log exists and has new entries
-------------------------------------------------------------------------------------------
No JSON output | Raw log message in console | Ensure stdout { codec => json } is in logstash.conf
--------------------------------------------------------------------------------------------------
File input plugin not working | Logstash not detecting new lines | Set sincedb_path => "NUL" in logstash.conf
-------------------------------------------------------------------------------------------------------------
