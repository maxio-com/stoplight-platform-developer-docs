---
tags: [Ecosystem]
---

# Overview

One of the many reasons to use Advanced Billing is the immense feature set and surrounding community.

## Integrations

Advanced Billing has partnered with many SaaS solutions to help you manage your business. The complete list of integrations is available [on Maxio.com](https://www.maxio.com/integrations).

For more information about existing integrations, please see this [Integrations help article](https://maxio-chargify.zendesk.com/hc/en-us/articles/5405429933069).

## Account

Your account can be reached upon logging in at [app.chargify.com](https://app.chargify.com/sso_login.html).

## Development

If you’re having difficulty executing a request via our API, try the simplest thing and attempt your request via the curl command-line tool, as shown in the below example. Add the `--verbose` flag to your request to receive even more debugging information.

Another handy tool is [Webhook.site](https://webhook.site/). You could send your request to their temporary URL instead of us to see visually what it is you’re sending, if you’re not sure.

While you can certainly write your own code to interact with Advanced Billing, it's likely someone has already written code for your platform.

### Security

**TLS/SSL**

Advanced Billing no longer supports TLS 1.0 or TLS 1.1 over HTTPS on the chargify.com domain. Any older browsers or API clients that do not support TLS 1.2 will no longer work. This change is mandated by the PCI Security Council and affects all merchants and service providers processing or transmitting credit card data.

For more information, please see our [help article on Security](https://maxio-chargify.zendesk.com/hc/en-us/articles/5404986900493).

**Payment Card Industry (PCI)**

For more information about our PCI auditing and related updates, please see our blog post, [What You Need to Know About PCI](https://www.maxio.com/blog/what-you-need-to-know-about-pci).

# API Reference

The complete API reference documentation is available [here](https://developers.chargify.com/docs/api-docs/YXBpOjE0MTA4MjYx-chargify-api).
