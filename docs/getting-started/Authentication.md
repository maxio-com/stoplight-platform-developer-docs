---
tags: [Getting Started]
---

# Authentication

Learn how to use API authentication to communicate directly with Advanced Billing from any programming language that you wish.

----------

There are two methods of authentication, depending on what you are accessing:

* [Chargify API](https://developers.chargify.com/docs/api-docs/YXBpOjE0MTA4MjYx-chargify-api) 
* [Chargify.js](./ZG9jOjE0NjAzNDI0-overview)

Both methods of authentication assume you have previously generated API keys securely stored them for later use. For more information, see ["Obtaining Credentials"](https://maxio-chargify.zendesk.com/hc/en-us/articles/5404829390349-Users#users-0-0).

## API

The first method of interaction is through the API. API Authentication is implemented as HTTP Basic Authentication over TLS (HTTPS).

Your API login credentials are not the same as the credentials you use to log in to the web interface. You must obtain your API credentials separately, and you must connect to the API via TLS 1.2 (or better).

One of the most common calls you will make via the API is to retrieve a list of subscriptions to retrieve additional information, such as the status of a specific subscription. A simple way to authenticate is to use the API Key as the _username_ and "X" as the _password_, like the following:

```
curl https://{subdomain}.chargify.com/subscriptions.{format} \
  -u '{API_key}:X' \
  -H 'content-type: application/json' \
  -X GET 
```

If passing the Basic Authentication header, the API key and password require base64 encoding:

```
curl --request GET \
  --url 'https:///{subdomain}.chargify.com/subscriptions.{format}' \
  --header 'authorization: Basic PDxhcGlfa2V5Pj46...' \
  --header 'content-type: application/json'
```

For more information about API authentication, please see our [API documentation/example](https://developers.chargify.com/docs/api-docs/YXBpOjE0MTA4MjYx-chargify-api#authentication).

----------

# Next Steps

After you've mastered authentication, you should check out the following articles:

* Managing [sites](./SitesSubdomains.md)
* Creating [products](./Products.md) and how they control what you bill customers
* Creating [subscriptions](../basics/Subscriptions.md), (ie. signing up customers)
