# Malware Protection Using an AWS Network Firewall

## Overview
Malware, short for malicious software, refers to any intrusive software developed by cybercriminals (often called hackers) to steal data and damage or destroy computers and computer systems. Examples of common malware include viruses, worms, Trojan horses, spyware, adware, and ransomware. Firewalls are like physical security walls situated between an organization's internal network and any external public networks such as the internet. The firewall protects an internal network from access by unauthorized users on an external network. Users need access to the internet for business reasons, but they can inadvertently download malware, which can impact network and data security. Malware threats can be present, and organizations can use various techniques and services to mitigate these threats (for example, firewalls, antivirus software, and user control best practice). This lab focuses on countermeasure techniques using a firewall.

## Environment
We have a pre-configured TestInstance (Amazon Elastic Compute Cloud [Amazon EC2]) instance to use to test access to the website hosting malicious files. This is contained in a perimeter zone and separated from the rest of AnyCompany’s important servers. You update the AnyCompany network firewall, create a rules group, and then attach that rules group to a firewall policy and the network firewall itself. You then log into the TestInstance and test the remediation.

## Task 1: Confirm Reachability
![malware downloaded](https://github.com/Cloud-Xplorer08/AWS-Network-Firewall/assets/71820244/b88d09de-9fb4-4373-8e4b-befc1eedd795)
We confirmed that the URL hosting the malware files is accessible through the current network and network firewall that AnyCompany is using. You used an isolated TestInstance EC2 instance to run commands and download the same malicious files that users downloaded. We need to fix the AnyCompany network firewall to stop access to this site.

Download Malware(URL 1- wget http://malware.wicar.org/data/js_crypto_miner.html)

Download Malware (URL 2- wget http://malware.wicar.org/data/java_jre17_exec.html)


## Task 2: Inspect the network firewall
![firewall created](https://github.com/Cloud-Xplorer08/AWS-Network-Firewall/assets/71820244/8b8a1b14-997c-4fdd-b38d-30b17302e5ec)

![edit statelesss action](https://github.com/Cloud-Xplorer08/AWS-Network-Firewall/assets/71820244/03b7143b-307c-494d-bcdb-e6b2d965ed24)
These settings now forward all packets to a stateful rule group for further inspection.

A stateful rules engine inspects packets in the context of their traffic flow, gives you the ability to use more complex rules, and gives you the ability to log network traffic and AWS Network Firewall firewall alerts on traffic. Stateful rules consider traffic direction. The stateful rules engine might delay packet delivery to group packets for inspection.

In this task, we inspected the network firewall and updated the firewall policy. You then updated the firewall policy to forward all packets for stateful rule inspection.

## Task 3: Create a firewall rule group



