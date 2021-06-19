# Authentication - Misconfigurations

### 1. Session Based Exploitation
- When you create a user, the application will check programmatically that the user does not exist by comparing the username provided with the existing user. 
- When you log in, the application will check that your username and password are correct, and then it will save your username in your session.
-  Finally, every time you will access the application, the application will retrieve your user's details based on the username provided in the session.
-  Tip: The trick here comes from the fact that the comparison when you create a user is done programmatically (i.e.: in Ruby) but when the user's details get retrieved, the comparison is done by the database. By default, MySQL (with the type `VARCHAR`) will perform a case insensitive comparison: "admin" and "Admin" are the same value.

- You can try logging in as "aDmin" or somthing similar by abusing the Case, and check if you can gain access.
-  If the user 'admin\[space\]' exists, you can add more spaces after 'admin'

### 2. 