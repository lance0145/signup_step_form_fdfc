# Simple API


## How to submit

1. You are required to have a Github URL to submit the coding test. Go create one if you haven't already.
2. Then, create a *private* repo to host the assignment and commit all the changes to that repo.
3. Grant access to the following Github users to assess your submission once you're done:
- antoniocarlosortiz
- nadinejamila


## Technical challenge

Build a simple RESTful web service on Django with the following API endpoints:

- Registration: the endpoint should accept email address (required), password (required), first name (optional), and last name (optional) of the user in JSON format.  On successful registration, the endpoint should respond with the created user object serialized in JSON format.  User account should be marked as inactive and email is sent to the email address with a token for activating the account. On error, the endpoint should respond with the reason for failure.

- User Activation: the endpoint should require the token as authorization for activation.  The user should be marked as active on success, and the serialized user object returned in the response.  On error, the endpoint should respond with the reason for failure.

- Login: the endpoint should require email and password, and if correct, responds with an OAuth2 bearer token.  Reason for failure should be returned on error.
See http://www.django-rest-framework.org/api-guide/authentication/#django-oauth-toolkit for recommended packages.

- Users list: the endpoint should respond with a list of all users in the system.  If a valid OAuth2 bearer token is supplied to access the resource then email, first name, and last name fields should be in the response data, along with other fields you think is nice to be returned.  If no authorization token was supplied, the email and last name fields should be omitted from the response data.

- Change password: the endpoint should validate the user’s current password before creating a new password.  A valid OAuth2 bearer token is required to access the resource.  Only the user's own password can be changed.

Please commit your solution to a public git repository and share the repository URL with us.  Please make sure to use the appropriate libraries, and use the best features of the libraries that you are going to use. e.g. for authentication here are the recommended packages: http://www.django-rest-framework.org/api-guide/authentication/#third-party-packages

For this exercise, we want to see how you layout your project, how you configure the frameworks, as well as what 3rd-party tools you will use, and how well you write your code.  We will also check how your project evolves via the git commits, so make sure you don't have only one commit with everything in the repository.

Good luck.


Best Practices:  
- Each endpoint should be a resource, not an action. Please read this: https://saipraveenblog.wordpress.com/2014/09/29/rest-api-best-practices/
- Demonstrate proper use of GET, POST, PUT, PATCH, DELETE.
- Return the response with the created object and with error messages showing the field name and the error details.


For example, if there are errors:
```
{
	“user”: null,
“errors”: [
	{
‘field’: ‘email’,
‘details’: ‘email already exists’
},
{
	‘Field’: ‘last_name’,
	‘details’: ‘field is required’
}
] 
}
```

For example, if a user was created:
```
{
	“user”: {
		“first_name”: “Juan”,
		“last_name”: “Dela Cruz”,
		“email”: “jd@gmail.com”,
},
“errors”: [] 
}
```
