# Phishing Email Investigation and Threat Intelligence

**Sean Lewis | Cybersecurity capstone portfolio**

Investigated four simulated emails, compared sender identities and authentication results, and produced evidence-based triage recommendations.

**Skills:** Email analysis · OSINT interpretation · payment-diversion risk · incident triage

**Status:** Completed lab write-up with documented evidence gaps.

> Controlled educational exercise. Findings describe the supplied evidence and do not imply a production incident.

## Business problem
Employees may be persuaded to disclose credentials, pay a false fee or redirect a supplier payment. This exercise evaluates four sample emails and explains a proportionate response.

## Method and findings
| Case | Evidence assessed | Assessment | Recommended action |
| --- | --- | --- | --- |
| Bank of America | Urgent reset request; lookalike secure-boa-alerts[.]cc destination; reported authentication failures | High-confidence phishing assessment | Quarantine; verify through a known bank channel; secure account if credentials were entered |
| Supplier invoice | US$47,250 request; changed bank details; sender and reply-address mismatch | Simulated supplier impersonation and payment diversion | Hold payment; call a known supplier contact; require second approval |
| Microsoft | Account-deletion threat; login-microsoft365-verify[.]top; inconsistent sender identities | High-confidence credential-harvesting assessment | Quarantine; review interaction and sign-in records; reset credentials and revoke sessions if exposed |
| DHL | US$2.99 redelivery fee; dhl-delivery-info[.]xyz; ZIP attachment reference | High-confidence shipping-themed phishing assessment | Verify delivery independently; inspect attachments safely; assess payment exposure |

### Threat-intelligence judgement
VirusTotal, AbuseIPDB, Shodan and MXToolbox screenshots are historical observations. Reputation scores and open ports provide context; they do not prove that an IP sent a message. Reported SPF, DKIM and DMARC failures in supplied or synthetic headers require corroboration from trusted mail records.

The bank sample's claimed sending IP is 91.108.56.122. The separate 185.220.101.47 address occurs in its body as an alleged intruder; it must not be substituted for the sender. In the DHL case, 176.111.174.55 is the claimed external sender and 176.111.174.33 is an earlier relay. The Microsoft AbuseIPDB screenshot has a search-box/result mismatch; the result panel identifies the address discussed.

## Results and business value
Four cases are documented. The invoice amount is an amount requested in a simulated email, not money saved. No real account compromise, payment loss, attachment execution or measured improvement in response time is established.

## Next evidence to collect
Obtain original message files and trusted gateway records; document link and attachment analysis in an isolated environment; record whether a user interacted with the message. The original message files and attachments are not included in this repository.

## Screenshot evidence

Original screenshots extracted from the supplied capstone PDF are shown below. Historical tool results have not been refreshed. Images are retained at their source resolution; click to inspect. The [evidence index](docs/evidence-index.csv) maps each image to its PDF page.

### PDF page 4, image 1

![Capstone evidence, page 4, image 1](assets/screenshots/page-04-image-01.png)

Figure A2. Shodan result for 91.108.56.122, the claimed sending IP. Hosting information and open ports do not establish malicious use. 

### PDF page 4, image 2

![Capstone evidence, page 4, image 2](assets/screenshots/page-04-image-02.png)

Original capstone screenshot, PDF page 4, image 2.

### PDF page 5, image 1

![Capstone evidence, page 5, image 1](assets/screenshots/page-05-image-01.png)

Figure A3. AbuseIPDB result for 91.108.56.122 showing a 9% score and two reports at the time captured.     

### PDF page 7, image 1

![Capstone evidence, page 7, image 1](assets/screenshots/page-07-image-01.png)

Figure A7. MXToolbox analysis displaying authentication and alignment failures for the bank-themed sample. This records the analysis  shown, not an independent verification of live delivery.      Finding and recommended response  The sender inconsistencies, lookalike reset link and urgent account-restriction story support a high- confidence phishing verdict. Quarantine the email and check the account through an independently  obtained bank app, website or telephone number. If credentials were entered, contact the bank  immediately and secure the account. No account compromise or loss is established by the supplied  records.     

### PDF page 9, image 1

![Capstone evidence, page 9, image 1](assets/screenshots/page-09-image-01.png)

Figure A8. AbuseIPDB result for 194.165.16.101 showing a 0% score and 42 historical reports. A low score does not authenticate the invoice.    Figure A9. Historical report entries for 194.165.16.101. shown in screenshot several port scan incidents and brute force attacks. 

### PDF page 9, image 2

![Capstone evidence, page 9, image 2](assets/screenshots/page-09-image-02.png)

Original capstone screenshot, PDF page 9, image 2.

### PDF page 12, image 1

![Capstone evidence, page 12, image 1](assets/screenshots/page-12-image-01.png)

Figure A10. Historical VirusTotal result for 185.220.101.47 showing 14 of 92 vendors flagging the IP.  

### PDF page 13, image 1

![Capstone evidence, page 13, image 1](assets/screenshots/page-13-image-01.png)

Figure A11. AbuseIPDB result panel for 185.220.101.47 showing 100% and 6,853 reports. The search box contains a different address; the  result panel identifies the IP discussed here.    This IP address has been reported a total of 6,853 times from 650 distinct sources. 185.220.101.47 was  first reported on September 22nd 2021, and the most recent report was 6 hours ago. In the last 60 days,  the top reporter locations were: Turkey with 59 reports; Germany with 47 reports; Netherlands with 22  reports. The most common categories in these recent reports were: Web App Attack 125 times; Hacking  84 times; Brute-Force 46 times; Port Scan 25 times; SSH 15 times; Other 54 times.   

### PDF page 13, image 2

![Capstone evidence, page 13, image 2](assets/screenshots/page-13-image-02.png)

Original capstone screenshot, PDF page 13, image 2.

### PDF page 14, image 1

![Capstone evidence, page 14, image 1](assets/screenshots/page-14-image-01.png)

Figure A12. Shodan information for 185.220.101.47, including a Tor-router service description. This does not identify the sender or prove  the email’s actual route.    Figure A13. MXToolbox analysis of the Microsoft sample showing reported authentication failures. Synthetic headers require corroboration  from trusted mail records.  Finding and recommended response  The lookalike verification address, inconsistent sender identities and deletion threat support a high-confidence  credential-harvesting verdict. Quarantine the email and review mail, web and sign-in records for actual interaction.  If credentials were entered, reset them and revoke existing sessions. Other measure include improved email  filtering, phishing-resistant multifactor authentication, suspicious-domain monitoring, employee phishing  awareness and documented incident response procedures     

### PDF page 14, image 2

![Capstone evidence, page 14, image 2](assets/screenshots/page-14-image-02.png)

Original capstone screenshot, PDF page 14, image 2.

### PDF page 16, image 1

![Capstone evidence, page 16, image 1](assets/screenshots/page-16-image-01.png)

Figure A14. Historical AbuseIPDB entry for 176.111.174.33, the earlier relay IP. This is a different address from the claimed external sender  ending in .55. 

### PDF page 17, image 1

![Capstone evidence, page 17, image 1](assets/screenshots/page-17-image-01.png)

Figure A15. AbuseIPDB result for 176.111.174.55 showing 0% and four historical reports. No recent reports does not establish that the email  is safe.     

### PDF page 18, image 1

![Capstone evidence, page 18, image 1](assets/screenshots/page-18-image-01.png)

Figure A16. MXToolbox analysis for the DHL sample showing reported authentication failures. The recorded policy and disposition do not  prove a real gateway’s behaviour.    Figure A17. Shodan result for the earlier relay 176.111.174.33, showing ports 80 and 443. Open web ports alone do not establish a phishing  service.  Finding and recommended response  Findings of the DHL Shipping Notification Email support a high-confidence classification of the message  as a shipping-themed phishing attempt. The inconsistent sender identity, lookalike link and fee request  support a high-confidence shipping-themed phishing verdict. Recommendations for targetcorp controls  include improved email filtering, suspicious-domain monitoring, attachment inspection, employee  phishing awareness and verification of shipment notifications through established courier channels. 

### PDF page 18, image 2

![Capstone evidence, page 18, image 2](assets/screenshots/page-18-image-02.png)

Original capstone screenshot, PDF page 18, image 2.

## Evidence and authorship
Source: *Cybersecurity capstone investigation*, Sean Lewis, dated 30 October 2026, supplied PDF, pages listed in the evidence index. This repository reorganises that work for portfolio review. It does not add claims of actions absent from the source. Original exports, message files, configurations and executable samples are not supplied.

## Further work
See the [validation checklist](docs/validation-checklist.md) for evidence to collect in a future authorised lab. Proposed checks are not completed results.

## Use and attribution
This portfolio documents Sean Lewis's capstone work. Third-party tool interfaces and trademarks remain the property of their respective owners. No blanket open-source licence is asserted for screenshots or third-party material.
