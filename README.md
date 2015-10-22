#Pay with Amazon Theme Integration for Mozu Core8#

This repository contains the full source files for the Mozu Core8 theme, with the required changes to enable Pay with Amazon on your Mozu storefront. If you are manually upgrading themes that extend earlier versions of the Mozu Core theme (Core4, Core5, Core6, or Core7), you can upgrade your entire theme from this repo. For your convenience, the full readme for Mozu Core Theme Version 8 is included at the bottom of this file.

##File Additions and Changes##

**Note:** Use GitHub’s [Compare Changes](https://help.github.com/articles/comparing-commits-across-time/) functionality to see full diffs of the following files.

The Pay with Amazon Integration adds the following files:
* `resources/images/amazonpay60x38.png`
* `scripts/modules/amazonpay.js`
* `scripts/modules/eventbus.js`
* `scripts/pages/amazon-checkout.js`
* `templates/modules/checkout/amazon-shipping-billing.hypr.live`
* `templates/pages/amazon-checkout.hypr`

And edits the following files:
* `labels/en-US.json`
* `scripts/pages/cart.js`
*	`scripts/pages/checkout.js`
*	`scripts/pages/location.js`
*	`scripts/pages/product.js`
*	`stylesheets/modules/cart/cart-table.less`
*	`stylesheets/modules/common/form-step.less`
*	`stylesheets/pages/checkout.less`
*	`templates/back-office/packing-slip.hypr`
*  `templates/email/order-confirmation.hypr`
*	`templates/email/order-refund-issued.hypr`
*	`templates/modules/cart/cart-table.hypr.live`
*	`templates/modules/checkout/checkout-payment.hypr.live`
*	`templates/modules/checkout/payment-selector.hypr.live`
*	`templates/modules/checkout/step-payment-info.hypr.live`
*	`templates/modules/checkout/step-shipping-address.hypr.live`
*	`templates/modules/page-header/utility-nav.hypr`
*	`templates/pages/checkout.hypr`
*	`package.json`
*	`theme.json`

Refer to the *Upgrading to Mozu Core Theme Version 8* section below for instructions/best practices for a theme upgrade.

##Additional Resources
* [Mozu Pay with Amazon Integration Using Arc.js](https://github.com/Mozu/PayWithAmazon) (Application Repo)
* [Pay with Amazon Configuration Guide](http://mozu.github.io/IntegrationDocuments/PayWithAmazon/Mozu-PayWithAmazon-App.htm) (In-app Documentation)
* [Mozu Theme Development Quickstart] (http://developer.mozu.com/content/learn/themedev/quickstart/create-your-first-theme.htm) (Mozu Documentation)
* [Intro to Arc.js](http://developer.mozu.com/content/arcjs/Arcjs_Intro.htm) (Mozu Documentation)
* [Comparing commits across time](https://help.github.com/articles/comparing-commits-across-time/) (GitHub Help) 

----------------------------------------------------
*Content below this line is from Mozu Core theme readme*

# Upgraded Mozu Core Theme

This release includes an upgraded Core theme called **Core8**.

## What's New

* A new Express Checkout workflow for quick checkouts
   - A new Default Payment setting for shoppers to enable Express Checkout
   - A new optimized Checkout workflow
* Anonymous order status checkout
* A new Theme Utility Bar for business users to view the store under different conditions
   - Future Date Preview so that you can view the future state of your content that has an Active Date Range
* A brand new SEO-friendly system for navigating categories and search results
   - A new `{% make_url %}` tag for creating crawlable URLs for every page state
   - Crawlable pagination links, sorting links, and faceting controls so that Web crawlers can understand more about your product catalog
   - Efficient, mobile-friendly HTML partial system on category and search pages
* A dynamic set of "reasons" for online RMAs, replacing the hardcoded set of reasons
* Numerous bugfixes
* Other enhancements listed in [Mozu Release Notes](http://developer.mozu.com/sites/default/files/feeds/learn/article_files/MozuQ22015ReleaseNotes.pdf).

## Upgrading to Mozu Core Theme Version 8

You must manually upgrade themes that extend Core4, Core5, Core6, and Core7 to use Core8 instead. We recommend user acceptance, automated unit, and end-to-end testing of your site to ensure Core8 works for your site.

Use the new [Mozu Theme Generator](http://npmjs.com/package/generator-mozu-theme) to create new themes **and to update existing themes!**

0. Examine the [merged Pull Requests](pulls?q=is%3Apr+is%3Aclosed) to see what individual features are coming over from Core.

0. Use the `yo mozu-theme` command to update your theme to inherit from Core8.

0. Once the generator is complete, you'll have a `references/core8` directory!

0. Merge the Core8 version of commonly overridden files, such as `stylesheets/storefront.less` and the outer Hypr templates.

0. Install your new Core8-based theme on a development sandbox and activate it.

0. Activate Debug Mode in the storefront by adding the query parameter `debugMode=true` to any storefront URL.

0. Visually examine your theme for problems. 

0. Test your site for issues: view a category, search for products, configure a product, manipulate the cart, check out and place an order, make changes to your account page, etc.

0. Make any necessary corrections based on visual errors or console errors.

0. Repeat the previous two steps until your theme is free from errors and regressions.
