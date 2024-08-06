# OWASP-Juice-shop-Broken-JWT-Authentication-

This report outlines the findings from a penetration test focused on the JWT authentication and hashing mechanisms in OWASP Juice Shop. The assessment uncovered a significant vulnerability where sensitive information, including user passwords, was exposed due to weak hashing practices. This issue was identified through the cracking of hashed tokens using Cracked Station.

**Scope**
Application: OWASP Juice Shop<br/>

Endpoints Tested: /api/Cards and related endpoints requiring JWT authentication.<br/>

Tools Used: Burp Suite, Online JWT decoder, Cracked Station.<br/>

1 ![burpe1](https://github.com/user-attachments/assets/3244750b-a59c-4134-bd67-fe254f98f0c5)<br/> 
Usage:
Burpe Suite was used to capture the HTTP requests between the client and the server. This allowed for a detailed inspection of the JWT tokens being transmitted.<br/>

**Steps:**
Set up Burp Suite as a proxy.<br/>
a Configure the browser to route traffic through Burp Suite.<br/>
b Capture and inspect the HTTP requests containing JWT tokens.<br/>
c Forwarding and Manipulating Requests- Burp Suite's Repeater and Intruder tools were used to modify and resend requests to test how the application handles various JWT tokens.<br/>
2 ![dev](https://github.com/user-attachments/assets/cc100ea1-83e4-4d3b-9302-5fe50f5697d3)
**Online JWT Decoder** <br/>
Usage:
Online JWT Decoder was used to decode the JWT tokens to understand their payload and verify the claims within them.
**Steps:**<br/>
a Copy the JWT token from the intercepted request.<br/>
b Paste the token into JWT.io to decode its header, payload, and signature.<br/>
c Inspect the claims within the payload for sensitive information.<br/>

3 ![finish](https://github.com/user-attachments/assets/09351473-a2c0-4c0d-acd8-4b27930f8fd3)
**Cracked Station** <br/>
Usage: Cracked Station was used to crack the hashed password values found within the JWT tokens.<br/>
**Steps:**<br/>
a Extract the hashed password from the JWT token.<br/>
b Submit the hashed value to Cracked Station for cracking.<br/>
c Analyze the results to obtain the plaintext password.<br/>
