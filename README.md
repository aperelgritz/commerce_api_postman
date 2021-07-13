# commerce_api_postman
Postman collection &amp; environment to query the new Salesforce B2C Commerce API

# Setup instructions:

Set your own values for the following environment variables:
- endpoint
- site_id
- shortCode
- organizationId (note: must be lowercase)
- clientId
- clientSecret
- tenantId
- locale
- shopper_login
- shopper_pass
- shopper_first_name
- shopper_last_name
- shopper_email
- shipping_method
- shipping_address
- shipping_city
- shipping_country_code
- shipping_post_code
- shipping_state_code

You will find your shortCode and organizationId in Business Manager:
Administration > Salesforce Commerce API Settingscommerce-api-settings
All other variables are set dynamically when you call the endpoints in order.
 

# Demo steps:

- Login as guest or registered customer: 00a or 00b
- Get customer account info and wishlist/gift registry: 01 & 02
- Search for public wishlists/gift registries: 03
- Search for products: 04 & 05
- Browse categories: 06 & 07
- Get product details: 08 & 09
- Create basket: 10a
- Add product to basket: 11a
- Checkout: 12a & 13a & 14a & 15a & 16a
- Prepopulate all basket details and content, alternative to 10a-16a (ie. one-page checkout): 10b
- Create order: 17
- Get data API access token (to update order statuses): 18
- Set payment status to 'paid' and order status to 'new' (otherwise the order stays 'created' and does not sync to OMS): 19 & 20


# Notes:

The product added to basket at 11a is the first product returned by 05 (product search) or 07 (category browse) - whichever you called last.
Some additional utility calls are provided with the 99 prefix.
If you get the error "Customer Baskets Quota Exceeded", call "99. Shopper Basket - Delete".
