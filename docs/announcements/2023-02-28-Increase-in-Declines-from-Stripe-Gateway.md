# 2023-02-28 Increase in Declines from Stripe Gateway

We have multiple merchants experiencing an increase in declines when storing credit cards within the Stripe payment gateway beginning in early February. Further investigation by our developers did not find any changes on our end that would result in these declines.

Until we receive more direct insight from Stripe on this matter, we recommend that any affected merchants contact Stripe directly. Additionally, customers encountering declines may reach out to their card issuing bank for more information. We have also found multiple instances where a decline succeeds in the future after some time, suggesting these declines may not be permanent errors.

We understand the inconvenience these increased declines may cause, and will provide further updates as soon as we have more information to share.

On March 9th, 2023, a feature was released that removes the temporary email submitted to Stripe by Chargify.js during the initial tokenization process.  During our developer's review, we compared requests made via Chargify's hosted Self-Service pages which were processing these cards with success versus the requests made via Chargify.js, only finding the temporary email as the common differentiation between these requests.

The feature in question was slowly rolled out to sites as requested. That being said, it appears that the rate of declined requests from Stripe has recently decreased for affected merchants independent of this feature, indicating that another change has likely occurred on Stripe's end.

As a result of these findings, we are marking this issue as resolved for the time being. Apart from the feature outlined above that was released proactively by our developers to hopefully aid in reducing the number of declines, no other changes were made on our end.

Additionally, due to the success rates increase without the need for this feature, we will not be rolling out the feature previously mentioned unless requested. If the feature to disable temporary Chargify.js emails is needed for your site's configuration, please reach out to Support.

If there are any additional questions on the cause of this issue, please reach out to Stripe support for further clarification as we are unable to verify the changes they made on their end to resolve this issue.
