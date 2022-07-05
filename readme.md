# spring security:

1) JWT (JSON web token) - for MicroService to MicroService Authorization.
2) OAuth - current standard for MicroService to MicroService Authorization.

2 ways to maintain a session using HTTP protocol is sessionId (maintaining session info on server side) & return a sessionId to client,
JWT token - contains header, payload & signature. This token containing the info is sent back to the client to be sent to server in any subsequent calls.
