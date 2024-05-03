# Cyber Yankee Day 1 Roadmap

This roadmap will give you the steps and tools needed to have a complete baseline of the Cyber Yankee network to be able to begin triaging the "Crown Jewels" of the enviorment. 

This is meant to be a very broad overview, please use additional playbooks for in depth analysis steps

## Day 1 Actions

Take these actions in this order, some of these can be done consecitvely as they can be assigned to a various Airmen depending on their Tier level or comfort with the tools. 

### CISO
1. [CISO Intial Actions](#ciso-initial-actions)

### Tier 1
1. [Network Enumeration](#network-enumeration)
1. [Vulnerability Scanning](#vulnerability-scanning)
1. [Subdomain Enumeration](#subdomain-enumeration)
1. [SIEM Alert Triage](#siem-alert-triage)
1. [Phishing Email Triage](#email-server-triage)

#### Tier 2
1. [User Account Baseline](#user-account-baseline)
1. [Admin Account Reviews](#admin-account-Reviews)
1. [Logging and Alerting Baseline](#logging-and-alerting-baseline)
1. [Firewall Rule Enumeration](#firewall-rule-enumeration)
1. [DNS Filtering](#dns-filtering)


### CISO Initial Actions

The CISO should immediately request the following actions be taken via the RFC process

1. Reset all users passwords, if this is not approved request all admin passwords to be reset at a minimum.
1. Request a full employee list from HR to compare against the users in Active Directory
1. Request Additional logging changes based on Tier 2 findings, Powershell, Cmd Line, and advanced Audit policy configuration logging at a minimum. 

### Tier 1 Actions

### Network Enumeration

Begin with a MassScan scan to identify all the IPs in the network and then use Nmap for additional in depth information we need to understand

- Number of devices of each VLAN
- Operating System fingerprint of all IPs
- Ports open on each IP
- Services running on these devices
- Software Versions

We can compare this to the network map that we are given and fill in the blanks, once we do that we can decide what is most important to triage. 

##### Tools: 
- NMAP, MassScan (Use Kali Linux for both tools)

##### Helpful Commands:

```
codeblocks
```

###### Documentation Links:
- (https://github.com/robertdavidgraham/masscan)
- (https://securitytrails.com/blog/masscan)

### Vulnerability Scanning

### Subdomain Enumeration

There is most likely going to be a internet facing web server. Anything internet facing that has 80 and 443 open we should be doing a subdomain scan to determine the threat landscape of that device. 

##### Tools:
- AMASS, Sublister (Use Kali Linux for both tools)

##### Helpful Commands:

```
codeblocks
```

###### Documentation Links:
- (https://securitytrails.com/blog/subdomain-scanner-find-subdomains)

### SIEM Alert Triage
 
 Have one to two Airmen begin reviewing the alerts already in Security Onion.

 ##### Suggestions:
- Review high and critical first
- Group alerts by computer name or IP, this can help build a story to understand what is happening
- Try different groupings or sortings, sort by amount of alerts, oldest to newest, etc. to find patterns.
- Compare alerts to parts of the MITRE ATT&CK Framework

##### Documentation Links:

### Phishing Email Triage

Once we have done an nmap we will be able to determine the email server either through the provided network map or by the OS scans or ports open like port 25 SMTP, 110 POP3, 143 IMAP. 

Depending on threat intelligence, there may be potential phishing emails based on past events. We should review these emails for potential phishing attempts like:

- malicious attachments or executables
- malicious links
- potential DLP issues

This can help point us to the intial access point of the red team. 

### Tier 2 Actions

Tier 2 will be handing System Administration, Active Directory, and Firewall. They may also assist Tier 1 as needed. 

### User Account Baseline 

Begin comparing user accounts in 

### Admin Account Reviews

### Logging and Alerting Baseline

We can assume there will be minimal logging and alerting set up on Day 1. Tier 2 should review what logging we have set up in the enviorment and work with the CISO to potentially get Sysmon turned on if possible. 

Additionally, Tier 2 should review Security Onion and make sure we have turned on the custom playbooks as well for additional alerting. 

Check for the following is being logged
- Windows event logs (security, audit, PowerShell, and command line is minimum)
- IDS/IPS logs
- Authentication logs 
- Firewall Logs
- DNS Logs
- Webserver logs
- Security Onion Playbooks
- Application Logs if applicable
- Cloud Enviorment Logs if applicable

Auditing wise we need the following turned on at a minimum. Work with the CISO on this. 
- Advanced Audit Policy Configurations by GPO
- All Powershell logging
- All command line process logging and auditing

##### Documentation Links:
(https://github.com/SwiftOnSecurity/sysmon-config)
(https://support.microsoft.com/en-us/topic/microsoft-security-advisory-update-to-improve-windows-command-line-auditing-february-10-2015-570edc4b-8ee7-950d-4629-045e308743e4)

### Firewall Rule Enumeration

### Active Directory Enumeration

### DNS Filtering

