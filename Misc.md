# Miscellaneous 
## 1. On Site Request Forgery (OSRF)
- Similar to cross site request forgery(CSRF) with OSRF an attacker can force a users web browser to make requests on the attackers behalf.
-  The only difference is that the request is initiated from the target application whereas CSRF is initiated from an attacker controlled site.

![](assets/code.png)

- The whole goal of this vulnerable application is to force the user to send a request to the “/admin/add” endpoint. Doing so will cause the application to add an admin user which the attacker could use to login to the victims application.
- Remember the goal is to make the user browser send a request to “127.0.0.1/admin/add?username=ghost&password=lulz”. This would create a new admin user called “ghost” with the password of “lulz”.
- Take a closer look at the “/” endpoint and how the “vuln_param” is used to create the src attribute of the image tag. What if an attacker were to input “../../”?
	 ![](assets/vuln.png)
	- As you can see above it caused the application to send a GET request to the path“/” instead of “/images”.
	
- The above request is a little better, if you look at the bottom right of the image you can see the browser make a request to “/admin/add.jpg”. If we add the username and password parameters we should be able to add an admin account as shown below:
	 ![](assets/adadmin.png)
	- Note when sending multiple parameters we must URL encode the “&” character otherwise the browser will think it belongs to the first request not the second. Also notice how the password is “lulz.jpg” and not “lulz”. This is because “.jpg” is appended to the string at the end to get rid of these characters in our password we can just add a dummy parameter as shown below:
		- http://127.0.0.1:5000/?vuln_param=../../admin/add?username=ghost%26password=lulz%26dummy_param=

		 ![](assets/admin.png)
		 
	 - Finally we are able to make a request to the “/admin/add” endpoint causing the application to add a new user called “ghost” with the password of “lulz”.

<hr>
## 2. Prototype Pollution
## 3. Client Side Template Injection
## 4. XML External Entity (XXE)
## 5. Content Security Policy Bypass
## 6. Relative Path Overwrite (RPO)

