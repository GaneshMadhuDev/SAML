# SAML

1. Security Assertion Markup Language (SAML) is a login standard that helps users access applications based on sessions in another context.
2. It’s a single sign-on (SSO) login method offering more secure authentication (with a better user experience) than usernames and passwords
3. Identity Provider — Performs authentication and passes the user's identity and authorization level to the service provider.
4. Service Provider — Trusts the identity provider and authorizes the given user to access the requested resource.

Benefits of SAML Authentication
===============================
   
1. Improved User Experience — Users only need to sign in one time to access multiple service providers. This allows for a faster authentication process and less expectation of the user to remember multiple login credentials for every application. In the example above, that user could have clicked on any of the other icons in their dashboard and been promptly logged in without ever having to enter more credentials!
2. Increased Security — SAML provides a single point of authentication, which happens at a secure identity provider. Then, SAML transfers the identity information to the service providers. This form of authentication ensures that credentials are only sent to the IdP directly.
3. Loose Coupling of Directories — SAML doesn't require user information to be maintained and synchronized between directories.
4. Reduced Costs for Service Providers — With SAML, you don't have to maintain account information across multiple services. The identity provider bears this burden.

How does SAML Authentication Work?
==================================

1. SAML single sign-on authentication typically involves a service provider and an identity provider.
2. The process flow usually involves the trust establishment and authentication flow stages.
3. This is the process flow:
=========================
The user tries to log in to Zagadat from a browser.
Zagadat responds by generating a SAML request.
The browser redirects the user to an SSO URL, Auth0
Auth0 parses the SAML request and authenticates the user. This could be with username and password or even social login. If the user is already authenticated on Auth0, this step will be skipped. Once the user is authenticated, Auth0 generates a SAML response.
Auth0 returns the encoded SAML response to the browser.
The browser sends the SAML response to Zagadat for verification.
If the verification is successful, the user will be logged in to Zagadat and granted access to the resources that they are authorized to view/modify.


SAML Process Flow diagram
=========================

ID: Newly generated number for identification
IssueInstant: Timestamp to indicate the time it was generated
AssertionConsumerServiceURL: The SAML URL interface of the service provider, where the Identity provider sends the authentication token.
Issuer: The EntityID (unique identifier) of the service provider
InResponseTo: The ID of the SAML request that this response belongs to
Recipient: The EntityID (unique identifier) of the service provider
