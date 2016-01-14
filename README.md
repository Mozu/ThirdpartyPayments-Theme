#ThirdParty Payment Theme Integration for Mozu Core8#

This repository is a branch of the ThirdpartyPayments-Theme repository, provided for backwards-compatibility. This repository contains the full source files for the Mozu [Core8](https://github.com/Mozu/core-theme/tree/core8) theme, with the required changes to enable Pay with Amazon and PayPal Express on your Mozu storefront. 

**Note:** This repo is NOT using the latest version of the Mozu Core theme. If you want to update your Mozu theme to match the latest Core, go to the master branch of this repo.


##File Additions and Changes

**Note:** Use GitHub’s Compare Changes functionality to see full diffs of the following files.

The Third-Party Payments Integration adds the following files:
* `resources/images/amazonpay60x38.png`
* `scripts/modules/amazonpay.js`
* `scripts/modules/eventbus.js`
* `scripts/modules/models-amazoncheckout.js`
* `scripts/modules/xpressPaypal.js`
* `scripts/pages/amazon-checkout.js`
* `templates/modules/checkout/amazon-shipping-billing.hypr.live`
* `templates/modules/checkout/payment-paybyamazon.hypr.live`
* `templates/pages/amazon-checkout.hypr`

And edits the following files:
* `labels/en-US.json`
* `scripts/modules/models-checkout.js`
* `scripts/pages/cart.js`
* `scripts/pages/checkout.js`
* `scripts/pages/location.js`
* `scripts/pages/product.js`
* `stylesheets/modules/cart/cart-table.less`
* `stylesheets/modules/checkout/checkout-payment.less`
* `stylesheets/modules/common/form-step.less`
* `stylesheets/pages/checkout.less`
* `templates/back-office/packing-slip.hypr`
* `templates/email/order-confirmation.hypr`
* `templates/email/order-refund-issued.hypr`
* `templates/modules/cart/cart-table.hypr.live`
* `templates/modules/checkout/checkout-payment.hypr.live`
* `templates/modules/checkout/payment-selector.hypr.live`
* `templates/modules/checkout/step-payment-info.hypr.live`
* `templates/modules/checkout/step-shipping-address.hypr.live`
* `templates/modules/common/email-address-summary.hypr.live`
* `templates/modules/page-header/utility-nav.hypr`
* `templates/modules/web-fonts-loader.hypr`
* `templates/pages/checkout.hypr`
* `package.json`
* `theme.json`  

##Additional Resources
* [PayPal Express Application by Mozu Configuration Guide](https://www.mozu.com/docs/guides/mozu-apps/paypal-express-app-by-mozu.htm)* 
* [Pay with Amazon Application by Mozu Configuration Guide](https://www.mozu.com/docs/guides/mozu-apps/pay-with-amazon-app-by-mozu.htm)*
* [Mozu Theme Development Quickstart](https://www.mozu.com/docs/developer/themes/quickstart.htm)

**Note:** You must log in with your Mozu Developer Account credentials to access content at [https://www.mozu.com/docs/guides](https://www.mozu.com/docs/guides/guides.htm)
