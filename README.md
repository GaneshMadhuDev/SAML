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

SAML Assertion
================
A SAML Assertion is the XML document that the identity provider sends to the service provider that contains the user authorization. There are three different types of SAML Assertions - authentication, attribute, and authorization decision. Authentication assertions prove identification of the user and provide the time the user logged in and what method of authentication they used (I.e., Kerberos, 2 factor, etc.) The attribution assertion passes the SAML attributes to the service provider - SAML attributes are specific pieces of data that provide information about the user. An authorization decision assertion says if the user is authorized to use the service or if the identify provider denied their request due to a password failure or lack of rights to the service.


Difference between OpenID and SAML
===================================
OpenID and SAML2 are both based on the same concept of federated identity. Following are some of the difference between them..
SAML2 supports single sign-out - but OpenID does not

SAML2 service providers are coupled with the SAML2 Identity Providers, but OpenID relying parties are not coupled with OpenID Providers. OpenID has a discovery protocol which dynamically discovers the corresponding OpenID Provider, once an OpenID is given. SAML has a discovery protocol based on Identity Provider Discovery Service Protocol.
With SAML2, the user is coupled to the SAML2 IdP - your SAML2 identifier is only valid for the SAML2 IdP who issued it. But with OpenID, you own your identifier and you can map it to any OpenID Provider you wish.
SAML2 has different bindings while the only binding OpenID has is HTTP
SAML2 can be either Service Provider (SP) initiated or Identity Provider (IdP) initiated. But OpenID always SP initiated.
SAML 2 is based on XML while OpenID is not.
Most of the application developed in last 3 years were only supporting OpenID Connect. 92% of the 8B+ authentication requests Microsoft Azure AD handed in May 2018 were from OpenID Connect enabled applications.

Difference between JWT and SAML
================================
Both SAML and JWT are security token formats that are not dependent on any programming language. SAML is the older format and is based on XML. It's used commonly in protocols like SAML-P, WS-Trust and WS-Federation (although not strictly required).
JWT (JSON Web Token) tokens are based on JSON and used in new authentication and authorization protocols like OpenID Connect and OAuth 2.0.

SAML Components
================
SAML consists of three sets of components: assertions, protocols and bindings. Assertions -- the statements of identity, authentication and authorization information -- as well as protocol messages, are all XML-formatted using the SAML specification. SAML protocols define how different entities request and respond to requests for security information.

Authentication in SAML
------------------------
Authentication validates the identity of the user, whether the user is valid or not.

Authorization in SAML
----------------------
Authorization determines whether user have specific permission or not, once the authentication is successful.

Identity Provider
-----------------
It does authentication and passes the user's identity and authorization level to the service provider.

SAML Service Provider
---------------------
SAML service provider is a service that receives and accepts authentication in combination with a single sign-on profile of the Security Assertion Markup Language (SAML).

Single Sign-On
--------------
Single sign-on ( SSO) is an authentication process that allows users to securely authenticate several applications and websites using only one set of credentials.

SAML uses Single-Sign On (SSO)
-------------------------------
SAML enables Single-Sign On (SSO), which implies that users can log in once, and same credentials can be re-used to log in to other service providers.

How Does SAML Work?
-------------------
SAML works by exchanging information about user's logins information, and attributes between the identity provider and service providers.

Each user logs in once to Single Sign On with the identify provider.
then the identify provider can pass SAML attributes to the service provider when the user attempts to access those services.
The service provider requests the authorization and authentication from the identify provider.
if the verification is successful, the user will be logged in.

Difference between SAML and OAuth?
----------------------------------
SAML provides enterprises with more control to keep their SSO logins safer, while OAuth is better on mobile which uses JSON.
OAuth uses a similar approach as SAML to exchange login information.
OAuth is a slightly more recent standard that has been co-developed by Google and Twitter to allow seamless internet login.
