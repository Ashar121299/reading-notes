## Permissions

Authentication or identification by itself is not usually sufficient to gain access to information or code. For that, the entity requesting access must have 
authorization.

Together with authentication and throttling, permissions determine whether a request should be granted or denied access.


### How permissions are determined

Permissions in REST framework are always defined as a list of permission classes.

Before running the main body of the view each permission in the list is checked. If any permission check fails, an exceptions.PermissionDenied or
exceptions.NotAuthenticated exception will be raised, and the main body of the view will not run.

When the permission checks fail, either a "403 Forbidden" or a "401 Unauthorized" response will be returned

### Object level permissions

REST framework permissions also support object-level permissioning. Object level permissions are used to determine if a user should be allowed to act on a 
particular object, which will typically be a model instance.

Object level permissions are run by REST framework's generic views when .get_object() is called. As with view level permissions, an exceptions.PermissionDenied
exception will be raised if the user is not allowed to act on the given object.

If you're writing your own views and want to enforce object level permissions, or if you override the get_object method on a generic view, then you'll need to 
explicitly call the .check_object_permissions(request, obj) method on the view at the point at which you've retrieved the object.

This will either raise a PermissionDenied or NotAuthenticated exception, or simply return if the view has the appropriate permissions.

### Setting the permission policy

The default permission policy may be set globally, using the DEFAULT_PERMISSION_CLASSES setting

## API Reference

### AllowAny

The AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.



### IsAuthenticated

The IsAuthenticated permission class will deny permission to any unauthenticated user, and allow permission otherwise.



### IsAdminUser

The IsAdminUser permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.



### IsAuthenticatedOrReadOnly

The IsAuthenticatedOrReadOnly will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method
is one of the "safe" methods; GET, HEAD or OPTIONS.


### DjangoModelPermissions

This permission class ties into Django's standard django.contrib.auth model permissions. This permission must only be applied to views that have a .queryset
property or get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned. The appropriate
model is determined by checking get_queryset().model or queryset.model.

### DjangoModelPermissionsOrAnonReadOnly

Similar to DjangoModelPermissions, but also allows unauthenticated users to have read-only access to the API.


### DjangoObjectPermissions

This permission class ties into Django's standard object permissions framework that allows per-object permissions on models. In order to use this permission class,
you'll also need to add a permission backend that supports object-level permissions, such as django-guardian.


## Custom permissions

To implement a custom permission, override BasePermission and implement either, or both, of the following methods:

.has_permission(self, request, view)
.has_object_permission(self, request, view, obj)
The methods should return True if the request should be granted access, and False otherwise.

If you need to test if a request is a read operation or a write operation, you should check the request method against the constant SAFE_METHODS, 
which is a tuple containing 'GET', 'OPTIONS' and 'HEAD'. 

## Overview of access restriction methods

REST framework offers three different methods to customize access restrictions on a case-by-case basis. These apply in different scenarios and have different 
effects and limitations.

1. queryset/get_queryset(): Limits the general visibility of existing objects from the database. 
2. permission_classes/get_permissions(): General permission checks based on the current action, request and targeted object. 
3. serializer_class/get_serializer(): Instance level restrictions that apply to all objects on input and output. 


## Third party packages 

- DRF - Access Policy

The Django REST - Access Policy package provides a way to define complex access rules in declarative policy classes that are attached to view sets or 
function-based views. The policies are defined in JSON in a format similar to AWS' Identity & Access Management policies.

- Composed Permissions

The Composed Permissions package provides a simple way to define complex and multi-depth (with logic operators) permission objects, using small and reusable 
components.

- REST Condition

The REST Condition package is another extension for building complex permissions in a simple and convenient way. The extension allows you to combine permissions
with logical operators.

-DRY Rest Permissions

The DRY Rest Permissions package provides the ability to define different permissions for individual default and custom actions. This package is made for apps
with permissions that are derived from relationships defined in the app's data model. It also supports permission checks being returned to a client app through the
API's serializer. Additionally it supports adding permissions to the default and custom list actions to restrict the data they retrieve per user.

-Django Rest Framework Roles

The Django Rest Framework Roles package makes it easier to parameterize your API over multiple types of users.

-Django REST Framework API Key

The Django REST Framework API Key package provides permissions classes, models and helpers to add API key authorization to your API. It can be used to authorize 
internal or third-party backends and services (i.e. machines) which do not have a user account. API keys are stored securely using Django's password hashing
infrastructure, and they can be viewed, edited and revoked at anytime in the Django admin.

-Django Rest Framework Role Filters

The Django Rest Framework Role Filters package provides simple filtering over multiple types of roles.

-Django Rest Framework PSQ

The Django Rest Framework PSQ package is an extension that gives support for having action-based permission_classes, serializer_class, and queryset dependent on 
permission-based rules.
