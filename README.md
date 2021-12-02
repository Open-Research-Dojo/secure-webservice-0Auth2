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
   
4. What are JWT tokens?
   - When should you use JWT tokens?
   - How do JWT tokens work?
   - Why use JWT tokens?
   

### 6. Method

Below are all the methods we used for this research. We will also assign everything to the questions. We will be using the <a href="https://ictresearchmethods.nl/Methods">DOT</a> framework as mentioned above.

- Literature study

### 7. Answers

1. Webservice

2. Auth0

3. 0AUth2

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

1. https://jwt.io/introduction
2. https://www.telerik.com/blogs/introduction-json-web-tokens-jwt
