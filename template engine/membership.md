# Template engine for membership

* **Membership:** A membership is created when a user signs up on your website. 
* **Subscription:** If your members pays a monthly or annual fee, that is a subscription. 

You might allow members without an active subscription. Or you might require a paid subscription with our without a free trial period.

## The "Me" page

The me page is where a signed in member can view info such as contact details and choose/change subscriptions and get receipts. 

To show the me page, create a new layout and call `[[ renderMemberArea() | raw ]]`. That will generate an HTML output with everything you need.
