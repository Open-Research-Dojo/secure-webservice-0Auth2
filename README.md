<img src="https://resources.yubico.com/53ZDUYE6/as/ft842hgc6brp7x4m4fk9s63/Auth0.gif" width="100%" height="400px"/>

# secure-webservice-0Auth2

## 1. About
This research is about making a secure webservice with 0Auth2.  

## 2. Acknowledgments

## 3. Contents

1. About
2. Acknowledgments
3. Contents
4. Foreword
5. Research
6. Method
7. Answers
8. Conclusion
9. Sources

## 4. Foreword

## 5. Research
Before the question can be answered properly we need to do some research about 0Auth2 and spring webservices. Also we will make some subquestions related to the main question. These questions will help us find a good conclusion. For this research we will be using the DOT framework.

### 5.1 Research questions


1. What is a webservice?  
   - What is a webservice?
   - What is spring?
   - How to setup a spring webservice

2. What is Auth0?
   - What is authorization in general?
   - Where is authorization used for?
   - Where is Auth0 used alot?
   - What is the flow of Auth0?
   - Conclusion

3. What is OAuth 2?
   - What is OAuth 2?
   - How does OAuth 2 work?
   - What are the pros and cons of OAuth 2?
   
4. What are JWT tokens?
   - When should you use JWT tokens?
   - How do JWT tokens work?
   - Why use JWT tokens?
   

### 6. Method

Below are all the methods we used for this research. We will also assign everything to the questions. We will be using the <a href="https://ictresearchmethods.nl/Methods">DOT</a> framework as mentioned above.

- Literature study

### 7. Answers

#### 1. Webservice

#### 2. Auth0

Authorization is the process of giving someone the ability to access a resource.
Of course, this definition may sound obscure, but many situations in real life can help illustrate what authorization means so that you can apply those concepts to computer systems. 
A good example is house ownership. The owner has full access rights to the property (the resource) but can grant other people the right to access it. You say that the owner authorizes people to access it. This simple example allows us to introduce a few concepts in the authorization context.
For instance, accessing the house is a permission, that is, an action that you can perform on a resource. Other permissions on the house may be furnishing it, cleaning it, repairing it, etc.
A permission becomes a privilege (or right) when it is assigned to someone. So, if you assign permission to furnish your house to your interior decorator, you are granting them that privilege. (What Is Authorization? - Examples and Definition - Auth0, 2021)

Now that we know what authorization is we will be diving deeper into authorization with Auth0. Auth0 is a flexible, drop-in solution to add authentication and authorization services to your applications. Your team and organization can avoid the cost, time, and risk that come with building your solution to authenticate and authorize users. In the docs of Auth0 (Understand How You Can Use Auth0, 2021), you can find a couple of good use cases if you want to implement Auth0.

1. Application with log in system (this includes social accounts). You also want to retrieve the customer's information so they can see their account information.
2. You are building an API and you want to secure it with OAuth2.
3. You built a JavaScript front-end app and a mobile app, and you want them both to securely access your API.
4. You want to enforce multi-factor authentication (MFA) when your users want to access sensitive data.
5. You want to monitor users on your site or application. You plan on using this data to create funnels, measure user retention, and improve your sign-up flow.
6. You want to act proactively to block suspicious IP addresses if they make consecutive failed login attempts, to avoid DDoS attacks.


Now let's take a look on how the flow works. Regular web apps are server-side apps where the source code is not publicly exposed, they can use the Authorization Code Flow (defined in OAuth 2.0 RFC 6749, section 4.1), which exchanges an Authorization Code for a token. Your app must be server-side because during this exchange, you must also pass along your application's Client Secret, which must always be kept secure, and you will have to store it in your client.

This is how it works according to Auth0 (2021): 

1. The user clicks Login within the regular web application.
2. Auth0's SDK redirects the user to the Auth0 Authorization Server (/authorize endpoint).
3. Your Auth0 Authorization Server redirects the user to the login and authorization prompt.
4. The user authenticates using one of the configured login options and may see a consent page listing the permissions Auth0 will give to the regular web application.
5. Your Auth0 Authorization Server redirects the user back to the application with an authorization code, which is good for one use.
6. Auth0's SDK sends this code to the Auth0 Authorization Server (/oauth/token endpoint) along with the application's Client ID and Client Secret.
7. Your Auth0 Authorization Server verifies the code, Client ID, and Client Secret.
8. Your Auth0 Authorization Server responds with an ID Token and Access Token (and optionally, a Refresh Token).
9. Your application can use the Access Token to call an API to access information about the user.
10. The API responds with requested data.

## 3. OAuth 2.0

### 3.1 What is OAuth 2

OAuth2, which stands for “Open Authorization”, is a standard designed to allow a website or application to access resources hosted by other web apps on behalf of a user. OAuth 2.0 provides consented access and restricts actions of what the client app can perform on resources on behalf of the user, without ever sharing the user's credentials. (What Is OAuth 2.0 and What Does It Do for You? - Auth0, z.d.)

So OAuth 2 doesn’t share password data but instead uses authorization tokens to prove an identity between consumers and service providers. For example, consumer being TikTok and service provider being Facebook, you can give TikTok permission to post a video from TikTok to Facebook without exchanging any credentials, you tell Facebook that it’s okay to give certain permissions to TikTok. OAuth 2 makes it possible to make one application run with another in a safe way.

### 3.2 How does OAuth 2 work?

#### Roles

An OAuth 2.0 flow has the following roles according to Auth0:

- <strong>Remember Resource Owner</strong>: Entity that can grant access to a protected resource. Typically, this is the end-user.
- <strong>Resource Server</strong>: Server hosting the protected resources. This is the API you want to access.
- <strong>Client</strong>: Application requesting access to a protected resource on behalf of the Resource Owner.
- <strong>Authorization Server</strong>: Server that authenticates the Resource Owner and issues access tokens after getting proper authorization.

#### Flow

Before OAuth 2 can be used, the Client must acquire its own credentials, a client id and client secret, from the Authorization Server in order to identify and authenticate itself when requesting an Access Token. 

Using OAuth 2, access requests are initiated by the Client, e.g., a mobile app, website, smart TV app, desktop application, etc. 

The token request, exchange, and response flow according to digital ocean:

1. The application requests authorization to access service resources from the user
2. If the user authorized the request, the application receives an authorization grant
3. The application requests an access token from the authorization server (API) by presenting authentication of its own identity, and the authorization grant
4. If the application identity is authenticated and the authorization grant is valid, the authorization server (API) issues an access token to the application. Authorization is complete.
5. The application requests the resource from the resource server (API) and presents the access token for authentication
6. If the access token is valid, the resource server (API) serves the resource to the application

![image](https://user-images.githubusercontent.com/33750291/150149276-7e609ebd-0eb5-4445-b955-2645af0e6381.png)
                                 Picture from Digital Ocean

### What are the pros and cons of OAuth 2?

#### Pros

<strong>Security</strong> - You can allow services such as Facebook to authorize companies such as ESPN.com to access the user profile without the need to share data subject’s access credentials as mentioned earlier. If a third-party site (in this example ESPN) gets a data leak, the Facebook user’s password remains secure.

<strong>Control</strong> - Not only does OAuth 2 give users the power to allow sites limited access to their data, but it even allows users to control when that timeframe window is up. It’s comforting that users can choose when authorization tokens expire.

#### Cons

Other then bad OAuth 2 implementations there are no cons for OAuth 2 except for the following:

<strong>Phishing</strong> - When performed correctly, OAuth 2 should be safe, but the fact that you can give permissions to others website so quickly can turn into a bad habit. Hackers/phishers can abuse the less educated net users into thinking they are logging in, but hackers/phishers are actually pishing your data.

#### 4. JWT Tokens

JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. (auth0.com, 2021)
JWT tokens are most commonly used for authorization purposes. This allows the user to access routes & services with permission with that token. Because a JWT token is compact it is a good choice to be passed in HTTP environments. 

When the user is authenticated a JSON Web Token will be created. When the user wants to access a protected route or service the user agent should send the token in the request. Tokens are send in the Authorization header using the Bearer schema. Protected routes or services will verify if the token is valid, if the token is verified the user is allowed to access those protected routes or services. 

JWT Flow
1. User signs in using a username and password.
2. Server verifies the credentials.
3. If user is authorized the server sends a token.
4. Browser receives the token and saves it in the cookies.
5. When the user requests a protected endpoint the JWT is passed in the HTTP authorization header.
6. The server verifies the JWT token.
7. The server permits the request.

These are some benefits of JWT tokens according to (auth0.com, 2021)
- JWT tokens are compact
- JSON parsers are common in most programming languages
- Ease of processing JWT tokens

### 8. Conclusion

### 9. Sources

1. https://auth0.com/intro-to-iam/what-is-authorization/
2. https://auth0.com/docs/get-started/auth0-overview#learn-more
3. https://auth0.com/docs/authorization/flows/authorization-code-flow
4. https://jwt.io/introduction
5. https://www.telerik.com/blogs/introduction-json-web-tokens-jwt
6. https://auth0.com/intro-to-iam/what-is-oauth-2/
7. https://www.varonis.com/blog/what-is-oauth
8. https://auth0.com/docs/authenticate/protocols/oauth
9. https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2
