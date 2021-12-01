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

3. What is 0Auth2?
   - Authentication or authorization?
   - What is the flow of 0Auth2?
   - When should 0Auth2 be used?
   - Is 0Auth2 safe?
   - How to setup 0Auth2?
   

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

#### 3. 0AUth2


### 8. Conclusion

### 9. Sources

1. https://auth0.com/intro-to-iam/what-is-authorization/
2. https://auth0.com/docs/get-started/auth0-overview#learn-more
3. https://auth0.com/docs/authorization/flows/authorization-code-flow
