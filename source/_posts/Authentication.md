---
title: Authentication
date: 2017-11-07 19:46:29
tags: dev
---

# Standards
- SAML (Security Assertion Markup Language)
  - XML based data format and protocol for user authentication
  - Oldest
- OpenID
  - Obsolete standard for maintatining identity with an identity provider.
  - Replaced by OpenID connect
- OpenID connect
  - Relies on OAuth 2.0 protocol for the User to grant the Service Provider access to their identity data
  - JSON Web Tokens to package identity and other claimns in the token payload
- OAuth 2.0
  - Authorization scheme not an authentication scheme
  - When you use OAuth for authentication you are using it to get authorization form the user to access their credentials stored with the provider and you are trusting the provider to have verified those credentials
-

# Single Sign On

- Single Point of Access is not the smae as a Signle Point of Failure
- Significant return on investment
  - reduce the strait on local it resources
- Enhance user satisfaction


# OAuth 2

## Definitions
- OAuth is a specification that allows users to delegate access to their data without sharing their username and password with that service
- OAuth allows notifying a resource provider (e.g. Facebook) that the resource owner (e.g. you) grants permission to a third-party (e.g. a Facebook Application) access to their information (e.g. the list of your friends).
- The OAuth 2.0 authorization framework enables a third-party application to obtain limited access to an HTTP service.
___

## Other useful information

OAuth allows for:

1. Different access levels: read-only VS read-write. This allows you to grant access to your user list or a bi-directional access to automatically synchronize your new LinkedIn friends to your GMail contacts.
2. Access granularity: you can decide to grant access to only your contact information (username, e-mail, date of birth, etc.) or to your entire list of friends, calendar and what not.
3. It allows you to manage access from the resource provider's application. If the third-party application does not provide mechanism for cancelling access, you would be stuck with them having access to your information. With OAuth, there is provision for revoking access at any time.


## Problems (Gotchas)

-


# Authorization vs Authentication

- Authentication is the process of verifying who you are. When you log on to a PC with a user name and password you are authenticating.
- Authorization is the process of verifying that you have access to something. Gaining access to a resource (e.g. directory on a hard disk) because the permissions configured on it allow you access is authorization.

- Authentication is the process of ascertaining that somebody really is who he claims to be.

- Authorization refers to rules that determine who is allowed to do what. E.g. Adam may be authorized to create and delete databases, while Usama is only authorised to read.


---
# Resources

[https://auth0.com/blog/everything-you-wanted-to-know-about-oauth-2-but-were-too-afraid-to-ask/](https://auth0.com/blog/everything-you-wanted-to-know-about-oauth-2-but-were-too-afraid-to-ask/)

[http://lightstep.com/blog/everything-I-wish-I-knew-about-enterprise-sso/](http://lightstep.com/blog/everything-I-wish-I-knew-about-enterprise-sso/)
