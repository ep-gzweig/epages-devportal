---
layout: post
title: "How to easily connect payment and shipping with online shops"
date: 2016-08-02
header_image: public/next-gen-webservices.jpg
category: tech-stories
tags: ["webservices", "third-party", "ecommerce", "payment", "shipping", "api"]
authors: ["Manel"]
about_authors: ["mmerino"]
---

In a [previous blog post](/blog/tech-stories/payment-integrations/), Xavi explained the standard payment flow model that we use for a long time.
In fact, flows between different payments or shippings have differences in architecture (SOAP or REST), as well as the requested data, and even the steps required.

## Standard flow for payments and shipping

But all of them have something in common:

*The online shop has to contact the web services from the final payment or shipping company, and provide the required information to make the payment or shipping.*

{% image_custom image="/assets/img/pages/blog/images/blog-next-gen-webservices-1.png" width="50" lightbox %}

From a development point of view, this approach can be OK if there are only a few payments and shippings to offer.
But this is not the case for ePages.
We're targeted to small and medium businesses.
We have many different merchants with different needs in many countries, and want to offer a broad range of payment and shipping options to fulfill their needs.
This can be a daunting task, because it means a lot of payments and shippings to integrate into ePages.
Furthermore, every single payment and shipping developed solution that we integrate needs to be adapted to changes performed by their companies because of improvements and/or new features offered by their web services.

## New approach available

Now, a new approach to connecting with payments and shippings for online shops is available.
That new model is being offered by a few startup companies, and the idea is as follows:

*The online shop has to contact the web services from the payment or shipping provider company, which is responsible to offer a portfolio of payment gateways/logistics.*

{% image_custom image="/assets/img/pages/blog/images/blog-next-gen-webservices-2.png" width="50" lightbox %}

Even though the basic idea for both, payment and shipping, is the same, they use different approaches to better fit merchant needs.

### Payments

Three asynchronous processes are required:

1. Merchant registers with final payment gateway in order to get credentials.
2. Merchant provides payment gateway credentials to payments provider company. Provider can then request payments to final payment gateway in the name of the merchant.
3. End users payment to final payment gateway through payment provider.

Steps one and two are onboarding tasks that have to be done only once.
Step three is the real payment process and includes many steps.

This is the flow of step 3:

{% image_custom image="/assets/img/pages/blog/images/blog-next-gen-webservices-3.png" width="50" lightbox %}

As you can see, the Payment Card Industry (PCI) compliance is guaranteed by the payments provider, and no matter the final payment gateway used, payment flow remains the same.

### Shipping

Processes and associated data flows for shipping are quite different than the ones for payments.

1. Merchant registers with shipping provider.
2. Shipping provider collects orders from merchant's shop.
3. Merchant requests offers to shipping provider for shipping an order from different logistics.
4. Merchant selects logistic offer and launches the shipping task.

Because there's no required contract between merchants and logistics, the onboarding process is simpler.
It only involves the merchant registration with the shipping provider.
But from the other side, three asynchronous shipping processes are required.

This is the flow of step 2:

{% image_custom image="/assets/img/pages/blog/images/blog-next-gen-webservices-4.png" width="50" lightbox %}

And the process for the merchants to make shipping requests to logistics from the shop's administration area, - step 4 - looks like this:

{% image_custom image="/assets/img/pages/blog/images/blog-next-gen-webservices-5.png" width="50" lightbox %}

## Summary

Because Logistic and Payment Gateway Companies don't have a standardized web services architecture, Payment and Shipping provider startup companies add great value, and probably this is why they are growing rapidly.

For ePages, it means that we can integrate a lot of payment methods and logistics very quickly, since there's minor or no effort at all in integrating additional payment gateways or logistics offered in their portfolios.
