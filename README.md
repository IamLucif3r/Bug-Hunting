![](Notes/assets/banner.gif)
<div align = "center"> <h1> Bug Hunting   </h1>	
A Collection of Notes, Methodologies, POCs, Tools and everything else related to Bug Hunting.  :v:

</div>

<br>

![](https://img.shields.io/twitter/follow/IamLucif3r_?style=social)     ![](https://img.shields.io/github/followers/IamLucif3r?label=Follow%20Me&style=social)  ![](https://img.shields.io/badge/Contribuitions-Welcome-brightgreen)



<hr>

:point\_right: A Bug Bounty Program is a deal offered by several Oragnizations & Individuals by which  recognition and compensation is provided to individuals for reporting Bugs. 

## Contents
:point\_right: The repo is organized in following manner. You can read the notes: 
1. [Reconnaissance - Phase 1](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance-%20Phase1.md)
	1. [CIDR Range](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance-%20Phase1.md#1-cidr-range)
	2. [Google Dorking](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Reconnaissance-%20Phase1.md#2-google-dorking)
	3. [Tools](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Reconnaissance-%20Phase1.md#3-tools---amass)
2. [Reconnaissance - Phase 2](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md)
	1. [Wordlists](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#1-wordlists)
	2. [Subdomain Enumeration](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#2-subdomain-enumeration)
		1. [Certification Transparency Logs](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#21-certification-transparency-logs)
		2. [Search Engine](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#22-search-engine)
		3. [Github](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#24-github)
		4. [Brute Force](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#25-brute-force)
		5. [Subdomain Permutation](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#26-subdomain-permutation)
		6. [Tools](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#27-tools)
	3. [DNS Resolutions](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#3-dns-resolutions)
	4. [Screenshot](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#4-screen-shot)
	5. [Content Discovery](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#5-content-discovery)
	6. [Inspecting JS Files](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#6-inspecting-js-files)
	7. [Google Dorks](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#7-google-dorks)
	8. [Conclusion](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Reconnaissance%20-%20Phase2.md#conclusion)
3. [Fingerprinting](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Fingerprinting.md)
	1. [IP](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Fingerprinting.md#1-ip)
	2. [Web-Application](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Fingerprinting.md#2-web-applications)
		1. [Wapalyzer](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Fingerprinting.md#22-wappalyzer) 	 
		2. [Firewall](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Fingerprinting.md#23-firewall)
	3. [Conclusion](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Fingerprinting.md#conclusion)
4. [Exploitation - Part 1](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md)
	1. [Subdomain Takeover](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#1-subdomain-takeover)
	2. [Github](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#2-github)
	3. [Misconfigured Cloud Storage Buckets](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#3-misconfigured-cloud-storage-buckets)
	4. [Elastic Search DB](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#4-elastic-search-db)
	5. [Docker API](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#5-docker-api)
	6. [Kuberneter API](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#6-kubernetes-api)
	7. [.git/.svn](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#7-git--svn)
	8. [Google Firebase](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%201.md#8-google-firebase-updated)
5. [Exploitation - Part 2](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md)
	1. [Exploiting CMS](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#1exploiting-cms)
	2. [Exploiting OWASP](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#2-eploitation-owasp)
		1. [XML Extended Entity (XXE)](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#21-xml-external-entity-xxe)
		2. [Cross Site Scripting (XXS)](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#22-cross-site-scripting-xss)
		3. [Server-Side Request Forgery (SSRF)](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#23-ssrf)
		4. [Cross Side Request Forgery (CSRF)](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#24-cross-site-request-forgery-csrf)
		5. [SQL Injection](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#25-sql-injection)
		6. [Command Injection](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#26-command-injection)
		7. [Cross Site Web Socket Hijacking (CSWSH)](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#27-cross-site-web-socket-hijacking-cswsh)
		8. [File Upload](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#28-file-upload-updated)
		9. [Directory Traversal](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#29-directory-traversal-updated)
		10. [Open Redirect](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#210-open-redirect-updated)
		11. [Insecure Direct Object Reference ](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Exploitation%20Phase%202.md#211-insecure-direct-object-reference-idor-updated)
6. [Methodology - Workflow](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Methodology%20-%20Workflows.md)
	1. [Traditional Workflow](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Methodology%20-%20Workflows.md#1-traditional-workflow)
	2. [Github Workflow](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Methodology%20-%20Workflows.md#2-github-workflow)
	3. [Cloud Workflow](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Methodology%20-%20Workflows.md#3-cloud-workflow)
	4. [Google Dork Workflow](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Methodology%20-%20Workflows.md#4-google-dork--workflow)
	5. [Leaked Credentials Workflow](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Methodology%20-%20Workflows.md#5-leaked-credentials-workflow)
	6. [Exploit Workflow](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Methodology%20-%20Workflows.md#6-exploit-workflows)
7. [API-Pentesting](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/API-Testing.md)
	1. [APIs](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/API-Testing.md#1-apis)
	2. [Authentication](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/API-Testing.md#2-authentication)
8. [Caching Servers](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Caching%20Servers.md)
	1. [Web Cache Poisoning](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Caching%20Servers.md#1-web-cache-poisoning)
	2. [Web Cache Deception](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Caching%20Servers.md#2-web-cache-deception)
9. [Miscellaneous](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Misc.md)
	1. [On Site Request Forgery (OSRF)](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Misc.md#1-on-site-request-forgery-osrf)
	2. [Prototype Pollution](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Misc.md#2-prototype-pollution)
	3. [Client Side Template Injection](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Misc.md#3-client-side-template-injection)
	4. [XML External Entity](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Misc.md#4-xml-external-entity-xxe)
	5. [Content Security Policy Bypass](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Misc.md#5-content-security-policy-bypass)
	6. [Relative Path Overwrite](https://github.com/IamLucif3r/Bug-Hunting/blob/main/Notes/Misc.md#6-relative-path-overwrite-rpo)

## Bug-Hunting Platforms 
Following are some of the top Bug-Hunting Platforms. You can make your account and start hunting bugs for the programs available.
- [Hackerone](https://www.hackerone.com/)
- [Bugcrowd](https://bugcrowd.com/)
- [Intigriti](https://www.intigriti.com/)
- Responsible Disclosures [(Use Google Dorks To Find Programs)](https://github.com/sushiwushi/bug-bounty-dorks/blob/master/dorks.txt)

<b>Note: This Repo is under development, Only Notes have been added till now. Separate Section for Tools, POCs and Tricks will be created soon</b>
### ➡️ Contributions
You are Welcome to Contribute. You can contribute by:
- Translating into other languages
- Adding more Methodologies, Tools, and other Resources.
- Just adding a star to our Github project :) 

 :point\_right: If you have some new idea about this Repository, issue, feedback or found some valuable tool feel free to open an issue or just DM me via [@IamLucif3r_](https://twitter.com/IamLucif3r_)
