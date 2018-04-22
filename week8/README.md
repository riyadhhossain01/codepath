# Project 8 - Pentesting Live Targets

Time spent: 14hours hours spent in total

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

Vulnerability #1: SQL Injection__
Entering the URL ![alt text](https://github.com/riyadhhossain01/codepath/blob/master/week8/SQL%20Injection%20Blue.gif)

First Select the Salesperson section, there is "?id=some number" at the end of the url, by entering a ' after some number (number can be from 1 to 9), the blue section will show "Database query failed" while the green and red sections just redirect resulting the blue section has SQLI vulnerability. I used ?id=' OR 1=1'-- etc to testify it.

Vulnerability #2: Session Hijacking__

Entering the URL ![alt text](https://github.com/riyadhhossain01/codepath/blob/master/week8/Session%20Hijacking:Fixation%20Blue.gif)

You will get a session token by logging in
Loggin out and loggin back in, the session token stays the same. However, the session token should change between each log out and log in (as is the case in the green and red site.


## Green

Vulnerability #1: Username Enumeration
Entering the URL ![alt text](https://github.com/riyadhhossain01/codepath/blob/master/week8/Username%20Enumeration%20Green.gif)

By loggin using a wrong username, the alert message is in plain text. But  loggin using a correct username, the alert message appeared is bold. By inspecting the page, we could found that class is "failure" for correct username. The other class is "failed" for uncorrect username.

Vulnerability #2: Cross-Site Scripting
Entering the URL ![alt text](https://github.com/riyadhhossain01/codepath/blob/master/week8/Cross-Site%20Scripting%20Green.gif)

In the Contact Us page, the script can be entered in Your Name and Feedback. For example, entering <script>alert('Shirong found the XSS!')</script> in both Your Name and Feedback, then go to feedback section in Staff Menu, the alert "Shirong found the XSS!" will appear twice. If you entern word instead of xss code in each section, then it will appear word.


## Red

Vulnerability #1: Insecure Direct Object Reference
Entering the URL ![alt text](https://github.com/riyadhhossain01/codepath/blob/master/week8/Insecure%20Direct%20Object%20Refrence%20Red.gif)

In the Find a Salesperson section https://35.188.56.136/red/public/salesperson.php?id=some number, by setting the number to be 10 or 11 will give two people that can't be found in Find a Salesperson section. But in blue or green site, when you enter id=10 or id=11, then it will go back to Find a Salesperson page.

Vulnerability #2: Cross-Site Request Forgery
Entering the URL ![alt text](https://github.com/riyadhhossain01/codepath/blob/master/week8/Cross%20Site%20Request%20Forgery%20RED%3CCSRF%3E.gif)

By trying to edit the information after changing the value of csrdf_token, red section is still able to make a change, while the other two sections show "Error: invalid request" after I changed its csrf_token.

Bonus Objective 2: Build on Objective #4 (Cross-Site Scripting)
Entering the URL ![alt text](https://github.com/riyadhhossain01/codepath/blob/master/week8/Build%20on%20Objective%20%234(CSS).gif)

In green section, I use <script>document.location="https://www.google.com"</script> in Feedback in Contact Us, then  I went to the feedback section in Staff Menu, it should direct the page to google. Additionally, type <script>alert(document.cookie)</script> may read the cookie data and type <script>document.cookie="username=abcde"</script>may set the cookie data.

## Notes

Describe any challenges encountered while doing the work
