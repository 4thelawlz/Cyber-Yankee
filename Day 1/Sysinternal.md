# Sysinternal Malware Analysis

Use the following tools to look for persistence and hidden malware running on a device.

## What To Look For

Look for:
1. No Icon
1. No description or company name
1. Unsigned, no verified signature
1. Plum Crazy Purple highlited in process explorer AKA Packed and encrypted executable
1. lives in unusuual places like Windows directory or User Profile
1. strange URLs in strings
1. Has open TCP connections
1. unknown unsigned or VT positive

## Autoruns

Look at:
1. Image path - anything out of the ordinary
1. known verified publisher
1. Filter by verified signatures

Tips:
1. uncheck and disable autorun before deleting, there may be additional autoruns that chain together to start that one. 

## Process Explorer

Look at:
1. turn on options > verified signature
1. see if there is a description and company name
1. check command line of the process 
1. Review strings
1. Review TCP Connections
1. Review Associated DLLs and Handles

Tips:

double click the process you are investigating and choose the string tab in under the properties pop up window. 

Review the strings in both memory and image, there is a radial button on the bottom to choose this. 

Next, choose the TCP/IP tab and review the network connections for that process.

Highlight the suspicious process and hit Ctrl + D and you will see all DLLs associated. check if they are verified and VirusTotoal

Hightlight the suspicious process and hit Ctrl + H This will show handles of process, which is what files needed for that executable to run. By doing this you can find files for persistence. 

in properties under image you can see the autostart location. hit explore and itll bring you to registry

## Process Monitor

1. Look at parent child process relationship - look for strange child processes


Tips:
Filter by category is write, this will show only modifications to the system. 

## TCP View

## Sigcheck

This will be used to check sginatures of exectuables and processes.

You will need to be in the file path you want to use the sigcheck tool in. Some suggested file paths

- C:\Program Files
- C:\Windows
- C:\Windows\System32

```
sigcheck -s -e -u * 
```

Tips:
If that command doesnt work remove the -s

## ListDLLs





