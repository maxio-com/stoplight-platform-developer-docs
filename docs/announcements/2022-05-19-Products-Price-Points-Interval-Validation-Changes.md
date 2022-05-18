# 2022-05-19 Products Price Points Interval Validation Changes

As of May 19th, 2022, validation on the `interval` attribute (POST/PATCH products/:id/price_points) is being changed.

Previously, we required the `interval` attribute to be greater than 0, so if you provided 0.5 value, there was a confused error message "Recurring interval: must be greater than 0.".

Now, we require this field to be greater than or equal to 1, so the message is "Recurring Interval: must be greater than or equal to 1.".
