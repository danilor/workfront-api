# workfront-api

This project is a CLONE from the original/official [WORKFRONT API](https://github.com/Workfront) library.

You can get more information about this API on the official APP.

## Why is this a clone?

Right now, Adobe Workfront is implementing a new way to authenticate with the workfront services different from API KEY and USERNAME and PASSWORD.
This way is using OAUTH2.0 authentication mechanisms to authenticate and
being able to use the API.

Sadly, it seems like the official Workfront API Node
Library does not support this new way of authentication, and the main issue here
is that the headers on the request cannot be modified at will.
So, the change was focused on
the API.ts file to add the "Authorization" header to the request.

That is the only change. This won't handle the OAUTH2.0 authentication by itself,
but it will allow you to add the header to the request.

To handle the OAUTH2.0 authentication, you will need to implement it by yourself using the
following link:

https://ims-na1.adobelogin.com/ims/token/v3 [POST]

[BODY]

```
{
    "client_id": "YOUR_CLIENT_ID"
    "client_secret": "YOUR_CLIENT_SECRET",
    "scope": "YOUR_SCOPE",
    "grant_type": "client_credentials"
}
```

## Usage

#### Server-side

Install as a dependency: `npm install --save workfront-api`.  
Then `require('workfront-api')` in your code. For example:

```javascript
const Workfront = require('workfront-api')

/**
 * The console.log statement below will output the following:
 * {
 *    Api: [Function: Api],
 *    ResponseHandler: { success: [Function: success], failure: [Function: failure] }
 * }
 */
console.log(Workfront)
```

## Documentation

API documentation is available at [http://workfront.github.io/workfront-api/](http://workfront.github.io/workfront-api/).
