## **1. Introduction**



Email phishing remains one of the most common and dangerous cyber-attacks targeting individuals and organizations. Attackers often spoof legitimate brands like PayPal to trick victims into clicking malicious links.

This project demonstrates how to analyze an email header using:



Google Admin Toolbox – Messageheader Analyzer



Raw mail header inspection



SPF, DKIM, and DMARC validation



Pattern recognition of phishing indicators



The goal is to determine whether the received email is legitimate or malicious.



## **2. Tools Used**

a) Google Admin Toolbox – Messageheader Analyzer



Used to parse and visualize the metadata inside an email header.



b) SPF, DKIM \& DMARC Verification



These authentication protocols help verify the legitimacy of the sender.



c) Raw Header File



phish\_sample\_raw\[2].txt — uploaded mail header for manual analysis.





phish\_sample\_raw\[2]



## **3. Screenshots Evidence**

3.1 Infosys Springboard – Power BI Course Page



(Screenshot confirming dashboard accessibility and learning progress)



3.2 Google Admin Toolbox – Messageheader Output



Key observations from the tool:



SPF: FAIL



DKIM: none



DMARC: FAIL



Sender hostname: unknownserver123.com



From address: account-security@paypaI.com

(notice the capital I instead of lowercase l—a classic phishing trick)



3.3 Email Routing Summary



Delay: 5 sec



Received from: unknownserver123.com



Delivered to: Gmail mail servers



## **4. Raw Header Analysis**



Below is the extracted header from the uploaded file:



From: PayPal Alert <account-security@paypaI.com>

Reply-To: security-team@secure-payment-check.com

Received-SPF: Fail

DKIM: none

DMARC: fail

Message-Id: <983274923847923874@unknownserver123.com>



4.1 Spoofing Indicators

Parameter	Result	Meaning

SPF	Fail	Sender IP is not authorized to send emails for PayPal

DKIM	None	Email is not cryptographically signed — suspicious

DMARC	Fail	Domain policy requires authentication, but it failed

Reply-To	Different domain	Redirects victims to attacker-controlled address

From domain	Faulty (paypaI.com)	Uses I instead of l — domain impersonation

Link in email	Fake URL	Visible link is PayPal but redirects to malicious site

## **5. Body Content and Phishing Indicators**

5.1 Email Body (HTML Extract)

Your PayPal account has been temporarily limited...

Click the link to verify: 

http://secure-paypal-verification-login.com/verify

(Displayed as https://www.paypal.com/verify)



5.2 Red Flags in the Body



Threatening urgency: "Verify within 24 hours… permanently restricted."



Display link ≠ actual redirect link



Fake domain mimicking PayPal security



## **6. Risk Assessment**

Category	Risk Level	Explanation

Credential Theft	High	Fake verification link

Identity Theft	High	Leads to phishing page

Financial Fraud	High	PayPal spoof

Malware Risk	Medium	Link may install malware

## **7. Final Conclusion**



The email is confirmed to be a phishing attempt.



All authentication checks — SPF, DKIM, and DMARC — failed, and the domain has multiple red flags, including impersonation and malicious links.



The email should be deleted, and no links should be clicked.



## **8. Recommendations**

✔ Strengthen Awareness



Always verify sender domains.



Avoid clicking links in unsolicited emails.



✔ Technical Controls



Enable strict SPF, DKIM, and DMARC for organizational domains.



Use mail filters to block known malicious IPs.



✔ Reporting



Report phishing attempts to:



Gmail: Report Phishing option



PayPal: phishing@paypal.com



## **9. Appendix**

9.1 Raw Header File



(Attached earlier)





phish\_sample\_raw\[2]



9.2 Screenshots Included



Infosys dashboard



Messageheader Analyzer results



Detailed routing and SPF/DKIM/DMARC failures

