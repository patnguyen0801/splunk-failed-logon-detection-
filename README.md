# Splunk Lab: Failed Logon Detection

## Objective
Detect failed authentication attempts in Windows Security logs using Splunk.

## SPL Query
```spl
index=main sourcetype=wineventlog LogName=Security EventCode=4625
| stats count by ComputerName, UserName
| where count > 3

## Screenshots
