# 2022-05-19 Products Price Points Interval Validation Changes

As of May 19th, 2022, validation on the `interval` attribute in products/price_points endpoint is being changed.

Previously, we required the `interval` attribute to be greater_than 1, so if you provided 0.5 value, there was a confused error message "Recurring interval: must be greater than 0.".

Now, we require this field to be greater_than_or_equal_to 1, so the message is "Recurring Interval: must be greater than or equal to 1.".
