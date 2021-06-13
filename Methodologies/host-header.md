# Host Header Injection
1. The first step is to check those pages, having Status code as:
	 - 200 or 300
	 - 201 or 301
	 - 202 or 302
	 - 203 or 303
	 - 204 or 304
 2. Intercept the request and send it to repeater. 
	 1.  <b>First Method:</b> Simply change the real Host to yahoo.com (it can be any website, in place of yahoo.com) and check if the webpage is being redirected or not.
	 2. <b>Second Method: </b> Change the host from realwebsite.com to google.com (or any other website) and set X-Forwarded-Host to realwebsite.com and check if the webpage is being redirected or not
	 3. <b>Third Method: </b> set X-Forwarded-Host to anywebsite.com  and Host to realwebsite.com and check if it is getting refirected or not.
	---
	
