# SDK challenge

Welcome to Bankin' / Bridge's SDK challenge.

In this challenge, you'll be writing a small set of functionalites for an SDK that implements the Bridge API (see: https://docs.bridgeapi.io)

You can choose to implement the SDK in any of those languages: Java, Python, Ruby, JS, Go.

For testing purposes, the `client_id` and `client_secret` of an existing Bridge app will be provided to you.

# Mandatory part

The SDK will provide two functionalities:
- 1 for registering a Bridge User (see: https://docs.bridgeapi.io/v2018-06-15/reference#user-resource)
- 1 for authenticating a Bridge User (see: https://docs.bridgeapi.io/v2018-06-15/reference#authenticate-a-user)

The interface of the SDK should be:

```
User        register(String email, String password)
UserSession authenticate(String email, String password)
```

with:

```
UserSession {
	User user;
	TokenSession session;
}
```

# Optional part

You may have noticed that `UserSession.user` is only partially populated because the authentication call to the API only returns part of the entity.

Upon trying to access / fetch an empty property of that entity, the SDK should automatically make the right call to the API in order to fetch the empty properties.
