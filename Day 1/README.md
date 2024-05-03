# Cyber Yankee Day 1 Roadmap

This roadmap will give you the steps and tools needed to have a complete baseline of the Cyber Yankee network to be able to begin triaging the "Crown Jewels" of the enviorment. 

## Day 1 Actions

Take these actions in this order, some of these can be done consecitvely as they can be assigned to a various Airmen depending on their Tier level or comfort with the tools. 

### CISO
1. [CISO Intial Actions](#ciso-initial-actions)

### Tier 1
1. [Network Enumeration](#network-enumeration)
1. [Vulnerability Scanning](#vulnerability-scanning)
1. [Subdomain Enumeration](#subdomain-enumeration)

#### Tier 2


### CISO Initial Actions

The CISO should immediately request the following actions be taken via the RFC process

1. Reset all users passwords, if this is not approved request all admin passwords to be reset at a minimum.
1. Request a full employee list from HR to compare against the users in Active Directory
1. 

### Tier 1 Actions

#### Network Enumeration

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

#### Vulnerability Scanning

#### Subdomain Enumeration

There is most likely going to be a internet facing web server. Anything internet facing that has 80 and 443 open we should be doing a subdomain scan to determine the threat landscape of that device. 

##### Tools:
- AMASS, Sublister (Use Kali Linux for both tools)

##### Helpful Commands:

```
codeblocks
```

###### Documentation Links:
- (https://securitytrails.com/blog/subdomain-scanner-find-subdomains)


