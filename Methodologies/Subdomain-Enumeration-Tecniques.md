# Subdomain-Enumeration Tecniques
- Sub-Domain Enumeration is the process of finding subdomains for one or more domain(s).
- Why ?
	- Hidden & Forgotten Sub Domains may lead to uncovering the critical vulnerabilities.
- Common Subdomain Enumeration Techniques:
	- Google Doriking
	- Using Specialized Searech Engine (e.g. VirusTotal)
	- Dictionary Based Enumeration
	- Sub-Domain Bruteforcing
	- Esoteric (Discussed Below)
		
## Techniques To be Covered:
- Certificate Transparency
- DNSSEC Zone Walking
- DNS Zone Transfer
- Passive Recon Using Public Datasets.

### 1. Certificate Transparency
- Under CT, a Certificate Authority will have to publis all SSL/TLS certificates they issue in a public log.
- Anyone can look throught the CT Logs and find the Certificates issued for the domain.
- Website: https://www.certificate-transparency.org
- All the SSL / TLS Certificates include the informations about the Subdomains, and all important information about a domain.
- How to search ?
	- https://crt.sh/
	- https://censys.io/
	- https://google.com/transparencyreport/https/ct/
	
---
