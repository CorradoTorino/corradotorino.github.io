---
layout: post
title: OAuth 2.0 and Access Tokens, All You Want to Know 
image: /assets/img/2021-04-12-fly-d-P3-YKLS2VKA-unsplash.jpg
tags: [security, authentication, authorization, OAuth, OpenID, tokens, JWT]
---
If you have worked with authentication and authorization of Apps and APIs, you have also played with tokens: access tokens, opaque tokens, JSON Web Tokens, bearer tokens… Here, I want to clarify the difference among these concepts and provide some simple guidelines to ensure their security.

![tokens everywhere](/assets/img/2021-04-12-tokens-everywhere.png)

In my previous post about [Authentication and Authorization with OAuth2 and OpenID Connect](https://corradocalzoni.com/2020-09-15-authentication-and-authorization-with-oauth2-and-openid-connect/)[^1], when explaining the difference among these two protocols, I quickly introduced the concept of tokens. However, I deliberately decided to handle its details in a separate post. In fact, I found a lot of confusion and misconceptions around this topic. But, if you don’t want to jeopardise all the effort done to protect your resources, a deep understanding of tokens is fundamental.

## The basic: What is an Access Token?

Simply said, an access token is a piece of information that grants access to a protected resource. 

I found very illustrative the analogy provided by Aaron Parecki comparing the OAuth access tokens to the hotel key cards[^2]. In fact, you get a hotel key card by authenticating at the front desk and you get an access token authenticating to an authorization server. You can use a hotel key card to access your room and eventually multiple other doors in the hotel. In the same way, an access token can be used to access different APis. A hotel key card can be used by anyone who can get a hold of it, and the same can be done with bearer access tokens. You can understand the severity reading  "The Danger of Bearer Tokens" section. A hotel key card expires at the end of your visit, and as explained in the section “Access Token Lifetime”, your APis should honor the expiration time defined by the authorization server. As hotel key cards can be revoked by the hotel at any time, the same is valid for the access token. As you can see, the analogy with the hotel key card is very powerful and I strongly recommend reading Aaron's [^2] to find out more parallelisms.

![hotel key card](/assets/img/2021-04-12-access-card-4575613_1920.jpg)

**An OAuth access token is the digital counterpart to an a hotel key card.**

## What is the difference between Opaque Tokens and JSON Web Tokens (JWT)? 

OAuth 2.0 allows delegation of authorization exchanging bearer access tokens among the different parties. However, OAuth 2.0 is totally open in their format. It just defines them as a string representing an access authorization. And they can be proprietary self-encoded serializations, JSON Web Token (JWT) or just random strings. 

Let’s start with **Opaque Tokens**: these are access tokens written in a proprietary format, they cannot accessed directly by the bearer[^5]. If the recipient of the token wants to validate an opaque token, he needs to call the server that issued the token. As you can understand there are no real rules about opaque tokens. 

A completely different story is for **JSON Web Tokens (JWT)**, these are strings representing a set of claims as a JSON object and are digitally signed to ensure their integrity[^4]. Unlike bearer tokens, JWTs are self-contained and their recipient can use and validate directly without calling the issuing server. JWTs, simply pronounced Jots, became very popular because OpenID Connect enforces their usage to inform identity information in the form of claims. 

![Jwt explained](/assets/img/2021-04-12-jwt-explained.png)
**Example of a Json Web Token (JWT).** On the left side, the JWT is encoded. On the right end, the same JWT has been decoded and highlighted its structure. The payload stores several claims. In this case, the “role” claim has been defined to identify the user role and the “scope” claim stores a set of authorization scopes.

## The Danger of Bearer Tokens

As mentioned, both OAuth 2.0 and OpenID Connect use bearer access tokens. Independently if we are talking about opaque tokens or JWTs, you need to be clear that anyone in possession of a bearer token can use it to get access to its associated resources[^3]. So, proper handling, storing and transport of bearer tokens is key to ensure security. Clients receiving tokens must ensure that they are not leaked to unintended parties. For example, presenting the token to an unauthenticated and unauthorized resource server or failing to validate the certificate chain will allow adversaries to steal the token and gain unauthorized access to protected resources. As threat mitigation, bearer token should be always exchanged with communication where confidentiality and integrity protection is ensured. For example, adoption of TLS connection with a validated TLS certificate chain is a must. 

Let’s consider the unfortunate situation where our bearer token has been leaked, although we did all the best to protect it. What can we do to mitigate the impact of the damage in this case? 

Firstly, it’s a good practice to **include in the token the identity of the intended recipients** (the audience scope)[^6]. In this way the stolen access token cannot be used with resource servers different from the one has been created for. For example, if you have a Google token with "audience" the calendar server, you cannot use the same token to access Gmail server. 

Secondly, another mitigation strategy is to design your system in order to have a **fine granularity of the authorizations**. In this way, the authorization server can provide scopes that guarantee access to limited resources. So, a stealing token cannot be used for requesting access to resources that exceed the indicated permissions. For example, let’s suppose you have a token that has been provided only to view the Calendar meetings, the same token cannot be used also for creating new meetings.

Finally, it’s advised to **use short-lived tokens** (on the order of minutes) in order to make the life of attackers harder. You can find more details on this point on the section "Token Lifetime".

## What Validate in a Token?

Taking in account that an access token is meant for an API, it then should be validated by the API for which it was intended[^7]. The client receiving a token, acting as a bearer, does not need to perform validation if it uses the token only in the request to the resource server. The client needs to validate the token only if it uses its content.

Of course, the resource server must validate the received access token, before consuming the information inside it[^8]. As mentioned before, opaque tokens can be validated only by the authorization server. On the other hand, JWT access tokens can be validated directly, without the need of the authorization server.

In the next table, I summarized the main validation that you can perform on the tokens. 

**Table with summary of main validations that can be performed on tokens.**

<table>
  <tr>
    <td><b>Validation</b></td>
    <td><b>Check to Perform</b></td>
    <td><b>Reason</b></td>
  </tr>
  <tr>
    <td>JWT Signature</td>
    <td>Is the token signed with the key of the authorization server?</td>
    <td>Ensuring token data integrity. The token was signed by the sender and not altered.</td>
  </tr>
  <tr>
    <td>Expiration Time</td>
    <td>Is the current datetime before the datetime in <i>"exp"</i> claim?</td>
    <td>Ensure the token is not expired. Short-lived tokens mitigate leak threats.</td>
  </tr>
  <tr>
    <td>Issued At Time</td>
    <td>Is the datetime in the <i>"iat" (issued at)</i> claim recent enough?</td>
    <td>Ensure the age of the JWT. However, usage of the "iat "claim is optional.</td>
  </tr>
  <tr>
    <td>Not Before </td>
    <td>Is the current datetime after the <i>“nbf”</i> claim?</td>
    <td>Ensure the JWT has become valid.</td>
  </tr>
  <tr>
    <td>Issuer</td>
    <td>Is the <i>"iss"</i> claim matching the expected authorization server issuer?</td>
    <td>Ensure the identity of the authorization server that issued the token</td>
  </tr>
  <tr>
    <td>Audience</td>
    <td>Is the <i>"aud"</i> claim matches the token consumer?</td>
    <td>Ensure the consumers for whom the token is intended. Limit token audience reduce impact of leaked token </td>
  </tr>
  <tr>
    <td>Scope</td>
    <td>Are the <i>“scope”</i> claims matching the requested resources?</td>
    <td>Restricting token usage to a specific scope reduces  token redirect threats, where attacker try to gain access to a different resource</td>
  </tr>
</table>


## Improve security with Key Rotation

Guaranteeing the signature of the access token is one of the security pillars of Oauth 2.0 and OpenID Connect. Applying cryptography in the correct way ensures a good degree of confidence. However, we often tend to forget that using the same old keys too frequently can allow hackers to succeed in their cryptanalysis resulting in the understanding of encoding and decoding patterns [^10]. 

In this direction, key rollover or key rotation has been identified as one of the best practices to secure private keys from being compromised. Key rotation is when a signing key is retired and replaced by generating a new cryptographic key. Industry standard recommends rotating keys in an automated fashion, for example Okta key rotation schedule is four times a year[^9].  

For sure, on top of an automatic rotation policy, you need also to rotate the key manually in case of emergency. For example, in the case you suspect that a private key has been leaked or you have suffered a security incident.

## How to deal with Token Lifetime?

To deal with token capture and replay, the lifetime of the token must be limited. One means of achieving this is by putting a validity time field inside the protected part of the token.  Note that using short-lived (one hour or less) tokens reduces the impact of them being leaked. Lifetimes of days or months must be avoided. If possible, short-lived access tokens should be combined with refresh tokens to improve security. In case of JWT, the claims *Expiration Time "exp"*,* Issued At "iat"* and *Not Before "nbf"* define the lifetime of the access token and must be taken into account according to the "Token Validation" chapter.

## Summary

I hope this post helped you to clarify some doubts about access tokens. We started easy from the basic concept on how they are used. And then we made clarity on the terminology around tokens. We appreciated the difference between opaque tokens and JWTs. We learned how much we need to care for our bearer tokens, and what we can do to reduce the damage when they are leaked. Then, we dive into more deep water, we have seen how we should validate the received token in order to trust only what really is worth. Finally, we learned how simple techniques such as signature key rotation can drastically improve the security of our authentication and authorization process. 

Now, it’s your turn. Send me a comment on my twitter or linkedin profile, you see on the bottom of the page, and send me your feedback. I'll be more than happy to engage with you.

## References and Useful Readings


[^1]: [Authentication and Authorization with OAuth2 and OpenID Connect:<br>](https://corradocalzoni.com/2020-09-15-authentication-and-authorization-with-oauth2-and-openid-connect){:target="_blank"} https://corradocalzoni.com/2020-09-15-authentication-and-authorization-with-oauth2-and-openid-connect
[^2]: [7 Ways an OAuth Access Token is like a Hotel Key Card:<br>](https://developer.okta.com/blog/2019/06/05/seven-ways-an-oauth-access-token-is-like-a-hotel-key-card){:target="_blank"} https://developer.okta.com/blog/2019/06/05/seven-ways-an-oauth-access-token-is-like-a-hotel-key-card
[^3]: [The OAuth 2.0 Authorization Framework: Bearer Token Usage:<br>](https://tools.ietf.org/html/rfc6750){:target="_blank"} https://tools.ietf.org/html/rfc6750
[^4]: [JSON Web Token (JWT):<br>](https://tools.ietf.org/html/rfc7519){:target="_blank"} https://tools.ietf.org/html/rfc7519
[^5]: [Access Tokens:<br>](https://auth0.com/docs/tokens/access-tokens){:target="_blank"} https://auth0.com/docs/tokens/access-tokens
[^6]: [OAuth 2.0: Audience Information:<br>](https://tools.ietf.org/id/draft-tschofenig-oauth-audience-00.html){:target="_blank"} https://tools.ietf.org/id/draft-tschofenig-oauth-audience-00.html
[^7]: [Common JWT security vulnerabilities and how to prevent them:<br>](https://connect2id.com/products/nimbus-jose-jwt/vulnerabilities){:target="_blank"} https://connect2id.com/products/nimbus-jose-jwt/vulnerabilities
[^8]: [The Hard Parts of JWT Security Nobody Talks About:<br>](https://www.pingidentity.com/en/company/blog/posts/2019/jwt-security-nobody-talks-about.html){:target="_blank"} https://www.pingidentity.com/en/company/blog/posts/2019/jwt-security-nobody-talks-about.html
[^9]: [Key rotation:<br>](https://developer.okta.com/docs/concepts/key-rotation/){:target="_blank"} https://developer.okta.com/docs/concepts/key-rotation/
[^10]: [A closer look at key rotation policies & OIDC:<br>](){:target="_blank"} https://dltlabs.medium.com/a-closer-look-at-key-rotation-policies-oidc-297361a9e3a7
