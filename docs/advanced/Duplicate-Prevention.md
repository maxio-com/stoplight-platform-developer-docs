---
tags: [Advanced]
---

# Duplicate Prevention

When making API requests, it is possible to receive an error even though your request actually completed successfully.

For example, if you submit an API request and it times out, you can’t be sure whether your request was received by Advanced Billing, or not.

If you simply re-try the request, you _might_ end up with a duplicate transaction.

## Uniqueness Token

In order to prevent these duplicates, Advanced Billing allows you to supply a `uniqueness_token` parameter in any `POST` or `PUT` request.

The value you supply for the `uniqueness_token` should be long and random, like a UUID. The exact format of the value is up to you.

If a subsequent request with the same uniqueness_token is received within 60 minutes, it will be rejected with a `409 Conflict` response code and a duplicate error message.

## Example

For example, suppose you are making an adjustment on a subscription. Using curl, you send the following POST request, including a `uniqueness_token`.

```json
curl --verbose -u $CHARGIFY_API_KEY:x -H Accept:application/json -H Content-Type:application/json -X POST \
-d @adjustment.json https://$CHARGIFY_SUBDOMAIN.chargify.com/subscriptions/$SUBSCRIPTION_ID/adjustments.json

adjustment.json:
    {"adjustment":
        {
          "amount": "-12.43",
          "memo": "Credit for outage on 1/31"
        },
        "uniqueness_token": "2731FB23-98AD-4489-BAF6-7D5CE916F766"
    }
```

After you send your request, there is some problem, and the request times out without a valid response instead of the `201 Created` you were hoping for.

Since you have supplied a `uniqueness_token`, you can safely re-try the request.

If you receive the expected `201 Created` (or `422 Unprocessable Entity`) response, you can continue as usual knowing that Advanced Billing never received your first request.

If you receive a `409 Conflict` and a duplicate error message for the re-try, then you know that the first request was received and responded to.

Example 409 Conflict response:

```
    < Status: 409 Conflict
    {"errors":["DuplicatePrevention::DuplicateSubmissionError"]}
    
```
Unfortunately, it is not possible to know what the outcome of the first request was, so you cannot automatically assume it was successful.

Depending on what type of request you were making, it might be possible to gracefully recover by recording some information about the original request, listening for webhooks, and matching up the webhook payload to find out whether the request succeeded or not.

In other cases, human intervention will be necessary.

## Summary

We hope this feature will help you prevent duplicate transactions during error handling.

That said, if you are experiencing repeated timeouts, please [open a support ticket](mailto:support@maxio.com) so we can investigate.
