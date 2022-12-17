##  JSON Web Tokens
### What is JSON Web Token?

JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON
object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private 
key pair using RSA or ECDSA.

### When should you use JSON Web Tokens?


- Authorization: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to 
  access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead
  and its ability to be easily used across different domains.

- Information Exchange: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using 
  public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload,
  you can also verify that the content hasn't been tampered with.

### What is the JSON Web Token structure?

- Header

  The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.
  
- Registered claims: These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them
  are: iss (issuer), exp (expiration time), sub (subject), aud (audience), and others.
  
- Public claims: These can be defined at will by those using JWTs. But to avoid collisions they should be defined in the IANA JSON Web Token Registry or be defined
  as a URI that contains a collision resistant namespace.

- Private claims: These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims.

- Signature

To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.


- Putting all together
  The output is three Base64-URL strings separated by dots that can be easily passed in HTML and HTTP environments, while being more compact when compared to 
  XML-based standards such as SAML.
  
![image](https://cdn.auth0.com/blog/legacy-app-auth/legacy-app-auth-5.png)

### How do JSON Web Tokens work?

In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned. Since tokens are credentials, great care must 
be taken to prevent security issues. In general, you should not keep tokens longer than required.

![image] (https://cdn2.auth0.com/docs/media/articles/api-auth/client-credentials-grant.png)

### Why should we use JSON Web Tokens?

As JSON is less verbose than XML, when it is encoded its size is also smaller, making JWT more compact than SAML. This makes JWT a good choice to be passed in HTML 
and HTTP environments.


## How to Use JWT Authentication with Django REST Framework

### How JWT Works?

The JWT is acquired by exchanging an username + password for an access token and an refresh token.

The access token is usually short-lived (expires in 5 min or so, can be customized though).

The refresh token lives a little bit longer (expires in 24 hours, also customizable). It is comparable to an authentication session. After it expires, you need a 
full login with username + password again.

### Installation & Setup

For this tutorial we are going to use the djangorestframework_simplejwt library, recommended by the DRF developers.

- pip install djangorestframework_simplejwt

#### settings.py

REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}

#### urls.py

from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]

### Usage

#### Obtain Token

First step is to authenticate and obtain the token. The endpoint is /api/token/ and it only accepts POST requests.

http post http://127.0.0.1:8000/api/token/ username=vitor password=123

#### Refresh Token

To get a new access token, you should use the refresh token endpoint /api/token/refresh/ posting the refresh token:

http post http://127.0.0.1:8000/api/token/refresh/ refresh=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2t


### What’s The Point of The Refresh Token?

At first glance the refresh token may look pointless, but in fact it is necessary to make sure the user still have the correct permissions. If your access token
have a long expire time, it may take longer to update the information associated with the token. That’s because the authentication check is done by cryptographic
means, instead of querying the database and verifying the data. So some information is sort of cached.

## Django Runserver Is Not Your Production Server

### A Production Stack

A production setup usually consists of multiple components, each designed and built to be really good at one specific thing. They are fast, reliable and very focused.

When a request arrives at your server, it should be passed to a dedicated web server. Nginx is an example for a good web server.

### How Does Django Fit In?

Your Django app does not actually run as you would think a server would - waiting for requests and reacting to them. Your project provides a uwsgi.py file, 
which contains a function to be called by the application server. This function gets a Python object representing the incoming request.

This function calls your code, and produces a response object which is passed to the WSGI server. There the response is translated into a HTTP response and is
passed back to the web server, which finally delivers it to the user.



