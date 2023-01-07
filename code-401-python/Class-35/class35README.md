## Authentication

### What is authentication?

Authentication is the process of determining whether someone or something is, in fact, who or what it says it is. Authentication technology provides access control for
systems by checking to see if a user's credentials match the credentials in a database of authorized users or in a data authentication server. In doing this, 
authentication assures secure systems, secure processes and enterprise information security.

### Why is authentication important in cybersecurity?

Authentication enables organizations to keep their networks secure by permitting only authenticated users or processes to gain access to their protected resources. 
This may include computer systems, networks, databases, websites and other network-based applications or services.

### How does authentication work?

During authentication, credentials provided by the user are compared to those on file in a database of authorized users' information either on the local operating 
system server or through an authentication server. If the credentials entered match those on file and the authenticated entity is authorized to use the resource, the 
user is granted access. User permissions determine which resources the user gains access to and also any other access rights that are linked to the user, such as during
which hours the user can access the resource and how much of the resource the user is allowed to consume.

### What is authentication used for?

User and process authentication are used to ensure that only authorized individuals or processes are allowed to access company IT resources. Depending on the use cases
for which authentication is used, authentication can consist of either SFA, 2FA or MFA.

The most common implementation of authentication is SFA, which requires a user ID and a password for sign-on and access. However, since banks and many companies now 
use online banking and e-commerce to conduct business and store customer Social Security and credit and debit card numbers, there is an increased use of 2FA and even 
MFA, which requires users and customers to enter not only a user ID and password, but also additional authentication information.

### What are authentication factors?

Authenticating a user with a user ID and a password is usually considered the most basic type of authentication, and it depends on the user knowing two pieces of 
information -- the user ID or username, and the password. Since this type of authentication relies on just one authentication factor, it is a type of SFA.

Strong authentication is a term that is typically used to describe a type of authentication that is more reliable and resistant to attack. Strong authentication 
typically uses at least two different types of authentication factors and often requires the use of strong passwords containing at least eight characters, a mix of 
small and capital letters, special symbols and numbers.

-Knowledge factor. The knowledge factor, or something you know, may be any authentication credentials that consist of information that the user possesses, including 
a personal identification number (PIN), a username, a password or the answer to a secret question.

-Possession factor. The possession factor, or something you have, may be any credential based on items that the user can own and carry with them, including hardware 
devices, like a security token or a mobile phone used to accept a text message or to run an authentication app that can generate a one-time password (OTP) or PIN.

-Inherence factor. The inherence factor, or something you are, is typically based on some form of biometric identification, including fingerprints or thumbprints, 
facial recognition, retina scan or any other form of biometric data.

-Location factor. Where you are may be less specific, but the location factor is sometimes used as an adjunct to the other factors. Location can be determined to 
reasonable accuracy by devices equipped with the Global Positioning System or with less accuracy by checking network addresses and routes. The location factor cannot
usually stand on its own for authentication, but it can supplement the other factors by providing a means of ruling out some requests. For example, it can prevent 
an attacker located in a remote geographical area from posing as a user who normally logs in only from their home or office in the organization's home country.

-Time factor. Like the location factor, the time factor, or when you are authenticating, is not sufficient on its own, but it can be a supplemental mechanism for 
weeding out attackers who attempt to access a resource at a time when that resource is not available to the authorized user. It may also be used together with 
location. For example, if the user was last authenticated at noon in the U.S., an attempt to authenticate from Asia one hour later would be rejected based on the 
combination of time and location.

![image](https://cdn.ttgtmedia.com/rms/onlineimages/security-multifactor_authentication.png)

### Authentication vs. authorization

Authorization includes the process through which an administrator grants rights to authenticated users, as well as the process of checking user account permissions
to verify that the user has been granted access to those resources. The privileges and preferences granted for an authorized account depend on the user's permissions
, which are either stored locally or on an authentication server. The settings defined for all these environment variables are established by an administrator.

### What are the different types of authentication?

Traditional authentication depends on the use of a password file, in which user IDs are stored together with hashes of the passwords associated with each user. 
When logging in, the password submitted by the user is hashed and compared to the value in the password file. If the two hashes match, the user is authenticated.

### User authentication vs. machine authentication

Machines also need to authorize their automated actions within a network. Online backup services, patching and updating systems, and remote monitoring systems, such
as those used in telemedicine and smart grid technologies, all need to securely authenticate to verify that it is the authorized system involved in an interaction 
and not a hacker.




