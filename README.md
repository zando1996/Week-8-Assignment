# Week-8-Assignment
# Project 8 - Penetration testing Live Targets

Time spent: **6** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL injection
 * In the salesperson info pages with the format "?id=XX" in the url, when tested by adding a ' to the end of the url, the red and green page simply redirect, while the green page shows a sql error message saying "Database query failed.". This gave away that the blue site had SQL Injection vulnerability, as shown in the gif walkthrough with a simple sleep command.


Vulnerability #2: SQL Injection
* The exploit exists in the salesperson.php page.
* The exploit is done via the url. 
* Using the given ```' OR SLEEP(5)=0--'``` statement, the page proceeds to wait 5 seconds before returning.


## Red

Vulnerability #1: Insecure Direct Object Reference
  * The salesperson database can be accessed by modifying the "?id=" tag in the url, and this can be used to access salespersons of id 10 and 11, while the publicly displayed data ends at id=9.

Vulnerability #2: Cross-Site Request Forgery 
  * The site accepts a post request from a different source that has a hidden form in it, and makes alterations to the user database.


## Green

Vulnerability #1: User Enumeration
 * When using a nonexistent username and a random password, the site's error message states "Log in was unsuccessful.". However, when using an existing/valid username and a random password, it shows the error message, but in bold "__Log in was unsuccessful.__".

Vulnerability #2: Cross-Site Scripting
  * This site's feedback form has a stored xss alert vulnerability. The script tag and code entered are executed when the admin checks the feedback.
