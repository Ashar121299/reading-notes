## Configuring Django Settings: Best Practices


### Managing Django Settings: Issues

- Different environments.  you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings 
  (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting 
  configurations.

- Sensitive data. You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This 
  data cannot be stored in VCS.

 -Sharing settings between team members. You need a general approach to eliminate human error when working with the settings. For example, a developer may add a 
 third-party app or some API integration and fail to add specific settings. On large (or even mid-size) projects, this can cause real issues.
 
- Django settings are a Python code. This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of 
  key-value pairs, settings.py can have a very tricky logic.
  
  
### Setting Django Configurations: Different Approaches

settings_local.py

This is the oldest method. I used it when I was configuring a Django project on a production server for the first time. I saw a lot of people use it back in the day, and I still see it now.

The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS.


### 12 Factors 

12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku,
a well-known Cloud hosting provider.

As the name suggests, the collection consists of twelve parts:

1. Codebase
2. Dependencies
3. Config
4. Backing services
5. Build, release, run
6. Processes
7. Port binding
8. Concurrency
9. Disposability
10. Dev/prod parity
11. Logs
12. Admin processes

### django-environ

we see that Django env variables are the perfect place to store settings so Writing code using os.environ could be tricky sometimes and require additional effort
to handle errors. It’s better to use django-environ instead.

Technically it’s a merge of:

- envparse
- honcho
- dj-database-url
- dj-search-url
- dj-config-url
- django-cache-url


### Setting Structure

Instead of splitting settings by environments, you can split them by the source: Django, third- party apps (Celery, DRF, etc.), and your custom settings.

### Naming Conventions

Naming of variables is one of the most complex parts of development. So is naming of settings. We can’t imply on Django or third-party applications, but we can follow these simple rules for our custom (project) settings:

- Give meaningful names to your settings.
- Always use the prefix with the project name for your custom (project) settings.
- Write descriptions for your settings in comments.



##  What Is SSH: Understanding Encryption, Ports and Connection

### What Is SSH?

SSH, or Secure Shell Protocol, is a remote administration protocol that allows users to access, control, and modify their remote servers over the internet.

### How Does SSH Work

The SSH key command instructs your system that you want to open an encrypted Secure Shell Connection. {user} represents the account you want to access.
For example, you may want to access the root user, which is basically synonymous with the system administrator with complete rights to modify anything on the 
system. {host} refers to the computer you want to access. This can be an IP Address (e.g. 244.235.23.19) or a domain name (e.g. www.xyzdomain.com).

### Understanding Different Encryption Techniques

The significant advantage offered by SSH over its predecessors is the use of encryption to ensure a secure transfer of information between the host and the client.
Host refers to the remote server you are trying to access, while the client is the computer you are using to access the host. There are three different encryption
technologies used by SSH:

1. Symmetrical encryption
2. Asymmetrical encryption
3. Hashing

### How Does SSH Work With These Encryption Techniques

The way SSH works is by making use of a client-server model to allow for authentication of two remote systems and encryption of the data that passes between them.

SSH operates on TCP port 22 by default (though SSH port can be changed if needed). The host (server) listens on port 22 (or any other SSH assigned port) for 
incoming connections. It organizes the secure connection by authenticating the client and opening the correct shell environment if the verification is successful.

![image](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-client-and-server.webp)
































