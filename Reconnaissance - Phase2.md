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
- 
- ![](assets/subdomain-enum.png)

#### 2.2 Search Engine
#### 2.3 Forward DNS
#### 2.4 Github 
#### 2.5 Brute Force
#### 2.6 Subdomain Permutation
#### 2.7 Tools
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