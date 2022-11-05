# Pen Testing Live Targets

Time spent: 6 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, 
then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: __________________

Description:

<img src="blue-vuln1.gif">


## Green

Vulnerability #1: __________________

Description:

<img src="green-vuln1.gif">


## Red

Vulnerability #1:**Insecure Direct Object Reference** -- One of the three sites is missing code which would prevent some sensitive information from being made public. 
Determine which color has the vulnerability. Then, figure out what the other two sites did correctly to prevent the information leak.

### Video Walkthrough

    Here's a walkthrough of this vulnerability:



Description:

<img src="red-vuln1.gif">
