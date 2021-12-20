# 2021-11-23 Issue Service Credit Response Body Change

As of November 23, 2021, the [Issue Service Credit API endpoint](https://developers.chargify.com/docs/api-docs/b3A6MTQxMDg0MTc-issue-service-credit) will respond with a new body:

```json
{
  "id": "Integer",
  "amount_in_cents": "Integer",
  "ending_balance_in_cents": "Integer",
  "entry_type": "String",
  "memo": "String"
}
```

Previously, this endpoint was returning just a status code with no body.