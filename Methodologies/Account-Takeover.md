# Account Takeover
### Method -1 
1. 1 account logged in 2 browsers
2. Tried signup with same account but showing email exist and redirect to signup page
3. In Firefox captured request of sign up submit >Do intercept > Response > Email exists
4. Response changed to E-mail available >302 found /dashboard. Account created
5. Change profile data
6. Refresh in chrome and data changed
Note: I didn't mention some things because I want you to implement your logic and do it by yourself.