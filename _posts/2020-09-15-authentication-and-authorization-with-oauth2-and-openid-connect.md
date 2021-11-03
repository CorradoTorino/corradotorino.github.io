---
layout: post
title: Authentication and Authorization with OAuth2 and OpenID Connect
thumbnail-img: /assets/img/2020-09-16-chris-panas-0Yiy0XajJHQ-unsplash_edited.jpg
share-img: /assets/img/2020-09-16-chris-panas-0Yiy0XajJHQ-unsplash_edited.jpg
tags: [security, authentication, authorization, OAuth, OpenID]
---
In this post I would like to highlight the distinctions among OAuth, OAuth2 and OpenId Connect. Following the historical evolution of these standards, we can better understand how we can use them for authentication and authorization.

In the last weeks I have been having fun developing an authentication server. I like security topics: there is a ton of stuff to learn. It is the typical field where the more you dig in the subject and more you feel to confirm the Socratic paradox: I know that I know nothing. Here I would profit and persist some known unknown topics that I moved in the bin of known known. 

Let’s start with some good news: if you want to deal with authentication and authorization of Api you do not have to break your head by choosing a protocol. OAuth2 and OpenId Connect are your friends.They are both mature and widely accepted in the community.
In particular, OAuth was born in the first decade of the century, where web services like Google were starting to provide the opportunity to share user information via Api. Therefore, authentication and authorization started to get traction. 

## What’s the problem?

Let’s make an example to frame the problem: you have the photo collection of your cat in Dropbox and you want to print them in VistaPrint, an online printing service. As you can imagine it will not be a good idea to give your Dropbox credentials to VistaPrint. Maybe a bored employee in VistaPrint could change your Dropbox password and make memes with your other photos. OAuth2 and OpenId are swiss knives to solve these situations. We’ll see in more detail how they solve the problem. For now, we can simplify saying: instead of sharing your credential, you share with VistaPrint a token with some minimum information: just the scopes needed to access your photos.

## From OAuth to OAuth2

As mentioned OAuth has grown old, it did a magnificent job but things change very fast and it was not able to stay with the time. Nowaday you can’t use OAuth anymore due to its limitations and vulnerabilities. But we need to be fair with him. When it was released in 2007 the world wide web was mainly a server to server communication and mobile phones were still not playing their role. Now, we have a completely different world: people sharing information from different types of devices, sensitive information shared outside the safe precinct of the enterprise playground, people interacting with applications that cannot be trustable and so on...

In order to overcome OAuth limitations, in 2012 OAuth2 came to stay. It was not a birth without pain. In fact the creation of the new standards highlighted the diatribe between the wild Web and the big companies of the enterprise worlds (Facebook, Microsoft, Google, Yahoo..). For sure, the resulting OAuth2 standard is not as simple and safer as wanted by its original leader Eran Hammer. In fact, OAuth2 and friends are way too hard for developers. And the decision to use bearer tokens and relying on SSL for their security undermined the entire concept. As a matter of fact, Eran withdrewes his name from the specification. Said that, we need to recognize that OAuth2 remains the key standardized framework for securing native mobile applications and API calls using secure access tokens.

## And from OAuth2 to OpenId Connect

It sounds like all our needs are solved with OAuth2.. Well not really! OAuth2 is an authorization protocol and its specifications are loose enough to be used also for authentication. However, also because its specifications are so loose it represents a challenge to get a good authentication implementation only using OAuth. Mainly, because each one can create its implementation, making interoperability harder. Only in 2014, the OpenID Connect (OIDC) standard was ratified in order to close the gap for authentication. OpenID Connect is a thin layer that sits on top of OAuth 2.0 that adds login and profile information about the person who is logged in. OpenID Connect enables scenarios where one login can be used across multiple applications, also known as single sign-on (SSO). I found quite illustrative the metaphor proposed by Justin Richer in an episode of Software Engineering Radio: Oauth2 is like having the ingredients of a cake, you can mix in different ways and bake it and you can probably obtain a good result. On the other hand, OpenID Connect is like having the receipt to bake a tasty and reproducible chocolate cake.
At the very end, the big difference between OpenID Connect and OAuth2 is the id_token. If we read the standard, it states: the ID Token is a security token that contains Claims about the Authentication of an End-User by an Authorization Server when using a Client, and potentially other requested Claims. The ID Token is represented as a JSON Web Token (JWT). In the next posts, we can see in more detail the concept behind the token, because it is the pillar of OAuth2 and consequently of OpenID Connect.

## References and Useful Readings 

1. [An Illustrated Guide to OAuth and OpenID Connect](https://developer.okta.com/blog/2019/10/21/illustrated-guide-to-oauth-and-oidc)
2. [SE Radio Episode 376](https://www.se-radio.net/2019/08/episode-376-justin-richer-on-api-security-with-oauth-2/) Justin Richer On API Security with OAuth 2
3. [SE Radio Episode 383](https://www.se-radio.net/2019/10/episode-383-neil-madden-on-securing-your-api/) Neil Madden On Securing Your API
4. [OAuth 2.0 leader resigns, says standard is 'bad'](https://www.cnet.com/news/oauth-2-0-leader-resigns-says-standard-is-bad/)
5. [The Road To Hell Is Authenticated By Facebook](https://www.darkreading.com/risk/the-road-to-hell-is-authenticated-by-facebook/d/d-id/1139181)
6. [OAuth vs. OpenID](https://www.gluu.org/blog/oauth-vs-openid-whats-the-difference/) What’s the difference?
7. [Understanding ID Token](https://medium.com/@darutk/understanding-id-token-5f83f50fa02e)
8. OpenID Connect [Specifications](https://openid.net/developers/specs/)
9. OAuth 2 [Specifications](https://tools.ietf.org/html/rfc6749)