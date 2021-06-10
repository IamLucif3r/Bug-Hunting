# Methodology - Workflow
Before you start trying to hack something you need to come up with a high-level plan of attack.

## 1. Traditional Workflow
This is the Traditional Workflow : <br>
![](traditional-workflow.png)
#### 1. Domain
- Pick a Company / Organization hosting the Bug Bounty Program.
- Locate all domains belonging to that company
- Perform DNS resolution to determine the A, NS, MX, and  NAME records of each target. (All A records should be added to a list of IPs belonging to the company.)

#### 2. CIDR
A CIDR range is just a range of IP addresses belonging to an organization.
- Large companies tend to have their own CIDR ranges but smaller companies will typically rent servers from a third-party vendor such as Rackspace or amazon web services (AWS) so they won’t have a CIDR range

#### 3. IP
- Perform a port scan of each port of the IP Addresses obtained. 
- If you don’t properly fingerprint each host you will be missing potential vulnerabilities.

#### 4. Web Application
- The final step in this recon process is to take the list of subdomains and IPs running a web application and  perform fingerprinting and content discovery on them.
	- For instance, if you see a site is running WordPress you might run a WordPress scanner on it. If you see an Apache Struts page you might try some known CVEs for that, the list goes on.
- After your fingerprint the host you will want to perform content discovery.
<hr>

## 2. Github Workflow
Sometimes developers will upload hard coded credentials in their source code and config files for the world to see. The workflow is: 
![Github Workflow](github-workflow.png)
- With a little recon you can find the repositories (used to manage and store the source code) and if you get lucky you will find some hard-coded credentials that can be used to login to their application or server.
<hr>

## 3. Cloud Workflow
The VPS, database, storage, and everything else can be hosted in the cloud. The workflow for Cloud Architecture is:<br>
![](cloud-workflow.png) <br>
Note: S3 buckets is a place to store files, it acts as your cloud storage.
- Sometimes companies will leave these open to the public allowing people to download sensitive data. AWS is not the only one impacted by this, nearly all cloud providers share this misconfiguration.
- check each cloud provider to see if your target has any assets with a misconfigured storage bucket.
<hr>

## 4. Google Dork  Workflow
Google dorks allow you to filter through the massive amount of data Google collects to find specific things, for example if you only want to show PDF
files hosted on an endpoint there is a dork for that. <br>
![](google-dork-workflow.png)
- Use google dorks to locate sensitive information on third party sites that a target uses.
<hr>

## 5. Leaked Credentials Workflow
This workflow might be out of scope. <br>
![leaked workflow](leaked-creds-workflow.png)
- First you must go out and find all of these database leaks. These can be downloaded for free by simply searching on google.
- The final step is to grep through these files for your target domain, something like the final step is to grep through these files for your target domain, something like “*@example.com”. After that is completed you should have a list of emails with their associated clear text password. After that is completed you should have a list of emails with their associated clear text password.
<hr>

## 6. Exploit Workflows

### 6.1 New CVE Workflow
- The second a new CVE drops with a working POC you want to be exploiting it. This workflow only happens every so often and you have to act fast when it does. <br>
![](cve-workflow.png)
- Let's say some dude named Orange drops a Palo alto firewall RCE exploit. You will need to figure out if your targets are running Palo alto so you can launch the exploit. You don’t want to go around trying to exploit everything as that would be foolish. Once you find some potential targets via fingerprinting you should launch the POC exploit code and wait to see if it worked.

### 6.2 Known Exploit / Misconfiguration Workflow
- The basic idea here is to fingerprint your targets assets so you can find known CVEs and misconfigurations impacting their technology stack.<br>
![](exploit-workflow.png)
-  For example, if your target is running apache struts then you may want to try launching some throwing some apache struts exploits at the target.
-  You need to fingerprint both the targets domains and IPs. Once that is completed you can search for public CVEs with working POCs. You’re not only looking for CVEs, you’re also looking for misconfigurations. CVEs get patched while misconfigurations can happen at any time to anyone.

### 6.3 CMS Workflow
- These exploits are generally bundled up as some sort of tool which scans for everything, this makes your life a lot easier as a tester, all you need to know is what tool to run for which CMS.<br>
![](cms-workflow.png)

### 6.4 OWASP Workflow
- If your hunting for XSS, SQLI, IDOR, file upload, or any other vulnerability it will should during this phase.<br>
![](owasp-workflow.png)

### 6.5 Brute Force Workflow
- This workflow involves brute forcing exposed admin interfaces, SSH services, FTP, services, and anything else that accepts credentials.<br>
![](brute-force-workflow.png) 
- Issue with this workflow is that many organizations will consider this type of attack out of scope so make sure to check

