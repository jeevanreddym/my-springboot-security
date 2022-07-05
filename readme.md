# spring security:

Authentication can be done against any Identity-Provider like LDAP, Active directory etc & once the user is verified as valid then the 
Principle contains the UserDetails along with the Authorities (Roles or Permissions i.e ADMIN, USER etc).

1) JWT (JSON web token) - for MicroService to MicroService Authorization.
2) OAuth - current standard for MicroService to MicroService Authorization.

2 ways to maintain a session using HTTP protocol is sessionId (maintaining session info on server side) & return a sessionId to client,
JWT token - contains header, payload & signature. This token containing the info is sent back to the client to be sent to server in any subsequent calls.



# Single Sign-On (SSO) is a process that enables a user to access multiple applications (the service providers) by logging in once on an authentication server (the identity provider).
![image](https://user-images.githubusercontent.com/26168295/177410774-41525b76-12d5-4e22-ad54-59e88b7c1430.png)

SSO gives access to many applications by entering credentials once.
Many applications are using this authentication system to allow users to login through another application's account, such as Google or Facebook's - on which they are used to keep a session open. For example, it is possible to login on Wordpress either through Wordpress' authentication server, or through SSO with a Google account.
Google itself enables its users to login with SSO to the multiple applications it provides - the service providers: Gmail, Youtube... - thanks to a unique central authentication server: Google Account - the identity provider.
