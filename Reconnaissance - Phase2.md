# Reconnaissance [Phase 2]
## 1. Wordlists
Word lists are used to find new subdomains, interesting files, cracking passwords, and much more.
#### 1.1 Sec List
- If you’re looking for a good wordlist this should be the first place you look, chances are they have the wordlist you're looking for.
	-  https://github.com/danielmiessler/SecLists
	-  <b>Robots Disallow</b>: The robots.txt disallow directory is used to tell scraping bots such as google to not crawl certain files and file paths, this can be a good indication that they are trying to hide something.
	-  <b>RAFT</b>: The RAFT wordlists contains a large number of interesting filenames and directories. There are several different versions of this list ranging in size but I generally just go with the largest list.
	-  <b>Technology Specific</b>:  Seclists contains specific wordlists for PHP, Golang, ASP, Apache, IIS, and a bunch more.
#### 1.2 Common Speak
- https://github.com/assetnote/commonspeak2
-  https://github.com/assetnote/commonspeak2-wordlists
-  Common speak from Assetnote has a unique way of generating wordlists. 
#### 1.3 All
- The majority of people use this wordlist for subdomain brute forcing.
- You won’t find a bigger word list than this one.
	-  https://gist.github.com/jhaddix/86a06c5dc309d08580a018c66354a056

#### 1.4 CRTSH
- Every https domain is logged in a database somewhere. Internetwache created a tool to scrape this database for subdomains. Every hour Internetwache uses this tool to update his wordlist.
	- https://github.com/internetwache/CT_subdomains	
	- 
<hr>

## 2. Subdomain Enumeration
#### 2.1 Certification Transparency Logs
- Any site that starts with HTTPS:// uses SSL certificates to provide a secure connection. If a hacker or rogue certificate authority is able to forge this certificate they would be able to perform man in the middle attacks.
- ![](assets/subdomain-enum.png)
- The certificate transparency log is used to monitor and audit unauthorized certificates. Every time you get an SSL certificate for your domain or subdomain it will be logged in certificate transparency logs
- We can find all SSL certificates belonging to a domain by issuing a GET request to https://crt.sh/?q=%25.facebook.com as shown below:
	- ![](assets/crt.png)
- <b>Tools</b>:
	- [Crtsh.py](https://github.com/ghostlulzhacks/CertificateTransparencyLogs)
#### 2.2 Search Engine
- Google dorks can be utilized to find subdomains with the following dork:
	- Site: 
		- This dork wil return all the links belonging to a specific domain. 
		 ![](assets/dork.png)
#### 2.4 Github 
- Almost every developer uses GitHub to store their source code. Developers will often hard code private or hidden endpoint points in their source code. 
- Tool : [Github-Search](https://github.com/gwen001/github-search/blob/master/github-subdomains.py) by [gwen001](https://github.com/gwen001).

#### 2.5 Brute Force
- Brute forcing is probably the most popular way to find subdomains. You might think that you send a get requests to a bunch of subdomains and see which ones resolve but that’s wrong. DNS can be used to brute force subdomains without sending packets to your target. All you do is perform a DNS requests against a subdomain if it resolves to an IP then you know it’s live. 
- <b>GoBuster</b>: [GoBuster](https://github.com/OJ/gobuster) is a good tool for discovering the directories hosted on a web server as well as a enumerating the Subdomains. 
	- It is however dependent on how good wordlist are you using for the enumeratoin.
#### 2.6 Subdomain Permutation
- One of the best ways to find hidden assets is through the use of permutations. A permutation is a way a set of words can be rearranged. 
- For example, if we have the subdomain test.starbcuks.com and the words dev, stage, and production we could come up with several possible subdomains. We would have dev-test.starbucks.com, dev.test.starbucks.com, production-test.starbucks.com, andso on. 
- All this can be done automatically with altdns:
	- [Altdns](https://github.com/infosec-au/altdns)
		- Using altdns we can pass in a list of found subdomains and a list of words and the tool will output a huge list of permutations. The tool can also resolve eachnewly found subdomain to see if they are live:
		- ``` 
		altdns -i found_subdomains.txt -o permutation_output -w words.txt -r -s resolved_output.txt ```
	- Other Tools: There are a lot of other techniques and resources that people can use to find subdomains.
		- Virus Total
		-  Netcraft
		-   DNSdumpster
		-  Threat crowed
		-  Shodan
		-  Cencys
		-  DNSdb
		-  Pastebin
		
#### 2.7 Tools
1. Amass:
	- 
2. 
<hr>

## 3. DNS Resolutions
<hr>

## 4. Screen Shot
<hr>

## 5. Content Discovery
#### 5.1 Self Crawl
#### 5.2 Wayback Machine Crawl Data
#### 5.3 Common Crawl Data
#### 5.4 Directory Brute Force
<hr>

## 6. Inspecting JS Files
#### 6.1 Link Finder
#### 6.2 JSearch
<hr>

## 7. Google Dorks
#### 7.1 Dork Basics
#### 7.2 Third Party Vendors
#### 7.3 Content
#### 7.4 