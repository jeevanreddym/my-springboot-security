# spring security:

Authentication can be done against any Identity-Provider like LDAP, Active directory etc & once the user is verified as valid then the 
Principle contains the UserDetails along with the Authorities (Roles or Permissions i.e ADMIN, USER etc).

1) JWT (JSON web token) - for MicroService to MicroService Authorization.
2) OAuth - current standard for MicroService to MicroService Authorization.

2 ways to maintain a session using HTTP protocol is sessionId (maintaining session info on server side) & return a sessionId to client,
JWT token - contains header, payload & signature. This token containing the info is sent back to the client to be sent to server in any subsequent calls.



Single Sign-On (SSO) is a process that enables a user to access multiple applications (the service providers) by logging in once on an authentication server (the identity provider).
![image](https://user-images.githubusercontent.com/26168295/177410774-41525b76-12d5-4e22-ad54-59e88b7c1430.png)
