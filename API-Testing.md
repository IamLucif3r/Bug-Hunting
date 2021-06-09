# API - Testing
- Most modern day applications are split into two sections, frontend and backend as shown below:
![](assets/brow.png)
- The backend is the API and can be written in multiple languages.
- There are several types of APIs and they are each slightly different so before you start API hacking you need to understand a few things.
![](assets/api.png)
## 1. APIs
### 1.1 Rest API
- 9 out of 10 times the API used is Rest API. Observe the request captured in burpsuite:
![](assets/reqa.png)
- First Sign telling the request is REST API is the fact that the request data is a JSON String.(JSON strings are widely used by REST APIs)
- The other sign is that the application is issuing a PUT request. The PUT method is one of several HTTP methods associated with REST APIs.
- Another sign you're dealing with a REST API is when the HTTP response contains a MIME type of JSON as shown in the below Burp requests:
![](assets/mime.png)
### 1.2 RPC - Remote Procedural Call
- oldest form of communication you will see being used by an application dating back to the 1980s.
-  This protocol is fairly basic, each HTTP request maps to a particular function.
![](assets/rpc.png)
- <b>Indicators</b>:
	- The first thing is the file name “xmlrpc.php”. XMLRPC uses XML while JSONRPC uses JSON for its encoding type. If this endpoint was an JSONRPC API the data would be contained in a JSON string instead of an XML doc, that's really the only difference between the two RPC APIs.
	- In the request body you see two tags called “methodCall” and “methodName” , since RPC requests correspond to function names so this is another hint at this being an RPC API.
	(Here we are calling the function “system.listMethods” and passing zero arguments.)
	- You know that REST APIs use several HTTP methods such as PUT,POST, and DELETE but RPC APIs only use two, GET and POST methods.

### 1.3 SOAP - Simple Object Access Protocol
- You can think of a SOAP API as a more advanced version of XMLRPC. They are both very similar by the fact they both use XML for encoding and HTTP to transfer messages.
- However, SOAP APIs tend to be a little more complex as shown in the below request:
![](assets/soap.png)
- the SOAP request is a little more structured and inorder to send a SOAP request you must follow this structure.
- An example of the SOAP format can be found below:
![](assets/env.png)
- The header part is optional and is used to hold values related to authentication, complex types, and other information about the message itself. The body is the part of the XML document which actually contains our message.
- Example:
```xml
<soapenv:Body>
	<web:GetCitiesByCountry>
		<!--type: string-->
		<web:CountryName>gero et</web:CountryName>
	</web:GetCitiesByCountry>
<soapenv:Body>
```
- As you can see in the above SOAP body we are calling a method named <b>“GetCitiesByCountry”</b> and passing in an argument called <b>“CountryName ”</b> with a string
value of <b>“gero et”</b>.

### 1.4 GraphQL API
- GraphQL is a data query language developed by Facebook and was released in 2015. GraphQL acts as an alternative to REST API.
- <b>Rest API v/s GraphQL</b>:
	- Rest APIs require the client to send multiple requests to different endpoints on the API to query data from the backend database. With graphQL you only need to send one request to query the backend.
- This means by default graphQL allows anyone to query it, any sensitive information will be available to attackers unauthenticated.
- When performing your directory brute force attacks make sure to add the following paths to check for graphQL instances: 
	-  /graphql
	- /graphiql
	- /graphql.php
	-  /graphql/console
-  Once you find an open graphQL instance you need to know what queries it supports. This can be done by using the [introspection system](https://graphql.org/learn/introspection/)
-  Issuing the following requests will show you all the queries that are available on the endpoint.
``` graphql
example.com/graphql?query=__schema{types{name,fields{name}}}}
```
![](assets/graph.png)
- Other than missing authentication by default graphQL endpoints can be vulnerable to other bugs such as IDOR.

## 2. Authentication
If an application requires you to login it must use some form of authentication to verify who you are. Depending on what authentication method an application is using there could be several types of attacks used to compromise the authentication process. Compromising the authentication process will typically lead to account takeover(ATO)
vulnerabilities
### 2.1 HTTP Basics
- This is probably the most basic and easy to implement type of authentication. As shown in the below image you can identify HTTP Basic Auth by the popup it displays in web browsers.
![](assets/auth.png)
- That's one of the biggest downfalls of using HTTP Basic Auth. Each time you send a request your clear text username and password are sent as a base64 encoded authentication header making it very susceptible to eavesdropping attacks.

### 2.2 Json Web Token
- extremely popular among API endpoints as they are easy
to implement and understand.
![](assets/jwt.png)
- a JWT token is made up of three parts separated by dots:
```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```
- The token can easily be decoded using a base64 decoder, but I like to use the site [jwt.io](jwt.io) to decode these tokens as shown below.
![](assets/jwtio.png)
- Notice how there are three parts to a JWT token:
	-  <b>Header</b> : this is where you specify the algorithm used to generate the signature.
	-  <b>Payload</b> : this is where you specify the information used for access control. In the above example the payload section has a variable called “name”, this name is used to determine who the user is when authenticating
	-  <b>Signature</b> : this value is used to make sure the token has not been modified or tampered with. The signature is made by concatenating the header and the payload sections then it signs this value with the algorithm specified in the header which in this case is “H256”.
- Without a signature anyone could modify the payload section completely bypassing the authentication process. If you remove the signature from a JWT token and it's still accepted then you have just bypassed the verification process. This means you can modify the payload section to anything you want and it will be accepted by the backend.
- this attack can be done manually or you can use a Burp plugin called “Json Web Token Attacker” as shown in the below image:
![](assets/json.png)

- <b> Brute Force Secret Key </b>: 
	- JWT tokens will either use an HMAC or RSA algorithm to verify the signature. 
	- If the application is using an HMAC algorithm it will use a secret key when generating the signature. If you can guess this secret key you will be able to generate signatures allowing you to forge your own tokens. 
	- There are several projects that can be used to crack these keys as shown below:
		- https://github.com/AresS31/jwtcat
		- https://github.com/lmammino/jwt-cracker
		- https://github.com/mazen160/jwt-pwn
		- https://github.com/brendan-rius/c-jwt-cracker
- <b> RSA to HMAC </b>: 
	- There are multiple signature methods which can be used to sign a JWT token as shown in the list below:
		-  <u><b>RSA</u></b>: When using RSA the JWT token is signed with a private key and verified with the public key. As you can tell by the name the private key is meant to be private and the public key is meant to be public.
		-  <u><b> HMAC</u></b>: HMAC is a little different, like many other symmetric encryption algorithms HMAC uses the same key for encryption and decryption.
		-   <u><b> None</u></b>: None 
		  
	- In the code when you are using RSA and HMAC it will look something like the following: 
		- verify(“RSA”,key,token)
		- verify(“HMAC”,key,token)
	![](assets/hmac.png)
	
