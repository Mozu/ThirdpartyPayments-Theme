#Third-Party Payments Theme Integration for Mozu Core9

This repository contains the full source files for the Mozu Core9 theme, with the required changes to enable both PayPal Express and Pay with Amazon on your Mozu storefront. These theme changes support the PayPal Express Application by Mozu and the Pay with Amazon Application by Mozu. Go to the Mozu App Marketplace to learn more about these apps and to request installation on your tenant.

If you are manually upgrading themes that extend earlier versions of the Mozu Core theme (Core5, Core6, Core7, or Core8), you can upgrade your entire theme from this repo. If you are not ready to upgrade your full theme, a version of these changes is also available in the [Core8](https://github.com/Mozu/ThirdpartyPayments-Theme/tree/Core8) branch of this repo.

**Tip:** Refer to the [Mozu Core Theme](https://github.com/Mozu/core-theme) readme for information about general updates included in Mozu Core9. The branches of the core-theme repo also include readmes for older versions of the Core Theme.

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
