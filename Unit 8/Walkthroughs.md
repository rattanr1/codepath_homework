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

Vulnerability #1: **SQL Injection** -- Most of the data input received by these websites is being sanitized properly. However, one of the three sites has one place where the input is not being sanitized before being used in an SQL query. Determine which color has the vulnerability.

### Video Walkthrough

    Here's a walkthrough of this vulnerability:

<img src="Vulnerability 1 - SQL Injection (Blue).gif">

Note:   What I put towards the end of the url for the specific salesperson
```
/blue/public/salesperson.php?id=%27%20OR%20SLEEP(5)=0--%27
```


Vulnerability #2: **Session Hijacking/Fixation** -- Two of the three websites expire their active sessions and require users to re-login every 30 minutes. That is probably too aggressive for the real world, but it is better than the third site which allows sessions to be a year old, and never regenerates the session ID, even when the user agent string changes. This makes it vulnerable to both session hijacking and session fixation attacks.

There are many ways an attacker could get or set the session ID in the real world (XSS, sniffing WiFi packets, etc.). For this exercise, a PHP script has been provided to help you, "public/hacktools/change_session_id.php". You can load this script to find out the current session ID or to set it to a new one.

Use two different web browsers (e.g., Firefox and Chrome). Let one browser be the attacker and the other the target. Choose if you want to attempt a session hijacking or session fixation. For hijacking, log the target in first, then give the logged-in session ID to the attacker. For fixation, get a session ID for the attacker, give it to the target, then the target will log in. In both cases, the attacker should now have access to the staff area.

### Video Walkthrough

    Here's a walkthrough of this vulnerability:

<img src="Vulnerability 2 - Session Hijacking- Fixation (Blue).gif"

Note: I opened up two Firefox tabs, one is BLUE and the other is RED. I logged into the BLUE site, and notice that the RED site was logged in as well!



## Green

Vulnerability #1: **Cross-Site Scripting** -- All three sites do a good job of protecting against a reflected XSS attack. However, one of the sites has a mistake which leaves the site vulnerable to a stored XSS attack. A reflected XSS attack would be easy to reveal, while a stored XSS does not provide instant feedback. You will need to log into the admin area and look through the CMS in order to "spring the trap" and find out if your attack succeeded. Determine which color has the vulnerability. Remember, others will be attacking these sites alongside you. Use your name in the XSS so that your results won't be confused with anyone else's (example: <script>alert('Mallory found the XSS!');</script>).

### Video Walkthrough

    Here's a walkthrough of this vulnerability:

<img src="Vulnerability 1 - Cross-Site Scripting (Green).gif">

Note: the false email shows up at the bottom, and I disabled the pop-ups that displays what I think was hundreds from other students doing this attack


## Red

Vulnerability #1:**Insecure Direct Object Reference** -- One of the three sites is missing code which would prevent some sensitive information from being made public. 
Determine which color has the vulnerability. Then, figure out what the other two sites did correctly to prevent the information leak.

### Video Walkthrough

    Here's a walkthrough of this vulnerability:

<img src="Vulnerability 1-Insecure Direct Object Reference (Red).gif">

Note: I noticed changing the numbers in the end of the URL results in different contacts for the  salesperson

