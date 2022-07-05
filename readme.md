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


# SSO Flow
To be authenticated through SSO on a service provider such as Gmail, one need to be logged in on the identity provider (Google Account), which provides a password-based authentication. Having that in mind, here is what the user journey might look like. users have to enter their credentials only once to be authenticated on 2 independent applications.


User browses to a service provider which uses SSO: www.service-provider-1.com.
www.service-provider-1.com redirects to the main authentication server: www.identity-provider.com. 
NB: The SSO process can be executed automatically by a redirection when browsing to www.service-provider-1.com, or manually by clicking on a button like “Continue with Google”.

www.identity-provider.com has no session open: User has not entered any credentials yet.
User is thus prompted with www.identity-provider.com ‘s login page.
User enters his credentials on www.identity-provider.com’s login page.
www.identity-provider.com authenticates User,
And redirects to www.service-provider-1.com with a signed token.
www.service-provider-1.com decodes the token and authenticates User.
www.service-provider-1.com displays its homepage to User.
NB: User did not have to enter his service-provider-1 credentials. He did enter his identity-provider credentials, that will allow him to access other service providers also using SSO: service-provider-2.

User browses to another service provider which uses SSO: www.service-provider-2.com.
www.service-provider-2.com redirects to the main authentication server: www.identity-provider.com. 
www.identity-provider.com has authenticated User earlier and still has his session open.
www.identity-provider.com redirects to www.service-provider-2.com with a signed token.
www.service-provider-2.com decodes the token and authenticates User.
www.service-provider-2.com displays its homepage to User.
Single sign-on needs the service providers to communicate with the identity provider. One way of exchanging user information is through Json Web Tokens (JWT).

NB: In this case, information must not be confidential, a token can be easily accessed and decoded with an XSS attack: do not communicate passwords through JWT!



