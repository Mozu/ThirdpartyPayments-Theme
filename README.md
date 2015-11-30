#Pay with Amazon Theme Integration for Mozu Core9#

This repository contains the full source files for the Mozu Core9 theme, with the required changes to enable Pay with Amazon on your Mozu storefront. These theme changes support the Pay with Amazon Certified Mozu Application, available from the [Mozu App Marketplace](https://www.mozu.com/ecommerce-app-center/). 

If you are manually upgrading themes that extend an earlier version of the Mozu Core theme (Core5, Core6, Core7, or Core8), you can upgrade your entire theme from this repo. If you are not ready to upgrade your full theme, the Core8 branch of this repo contains the Pay with Amazon changes for Mozu Core theme version 8. 

For your convenience, the full readme for Mozu Core Theme Version 9 is included at the bottom of this file.

##File Additions and Changes##

**Note:** Use GitHub’s [Compare Changes](https://help.github.com/articles/comparing-commits-across-time/) functionality to see full diffs of the following files.

The Pay with Amazon Integration adds the following files:
* `resources/images/amazonpay60x38.png`
* `scripts/modules/amazonpay.js`
* `scripts/modules/eventbus.js`
* `scripts/modules/models-amazoncheckout.js`
* `scripts/pages/amazon-checkout.js`
* `templates/modules/checkout/amazon-shipping-billing.hypr.live`
* `templates/modules/checkout/payment-paybyamazon.hypr.live`
* `templates/pages/amazon-checkout.hypr`

And edits the following files:
* `labels/en-US.json`
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
* `templates/modules/page-header/utility-nav.hypr`
* `templates/pages/checkout.hypr`
* `package.json`
* `theme.json`

Refer to the *Upgrading to Mozu Core Theme Version 9* section below for instructions/best practices for a theme upgrade.

##Additional Resources

* [Pay with Amazon Configuration Guide](http://mozu.github.io/IntegrationDocuments/PayWithAmazon/Mozu-PayWithAmazon-App.htm) (In-app Documentation)
* [Mozu Theme Development Quickstart](http://developer.mozu.com/content/learn/themedev/quickstart/create-your-first-theme.htm) (Mozu Documentation)
* [Mozu Pay with Amazon Integration Using Arc.js](https://github.com/Mozu/PayWithAmazon) (Application Repo)
* [Intro to Arc.js](http://developer.mozu.com/content/arcjs/Arcjs_Intro.htm) (Mozu Documentation)
* [Comparing commits across time](https://help.github.com/articles/comparing-commits-across-time/) (GitHub Help) 

----------------------------------------------------
*Content below this line is from Mozu Core theme readme*

This release includes an upgraded Core theme called **Core9**.

## What's New

* Significant usability enhancements to the cart and checkout workflow:
   - Edit a saved shipping address during checkout.
   - Simplified removal of digital wallet payment information.
   - Applied shipping method now shows full list of shipping options.
* Upgraded PayPal Express payment experience, with support for separate authorization and capture:
   - Removed the old version of PayPal Express support from the Core Theme. 
   - Forked a new theme with support for the new PayPal Express Certified Mozu Application.
* Improvements to the theme creation and upgrade process:
   - We've officially deprecated the `extends` directive in `theme.json`. It will continue to work, but rather than using runtime resolution of your base theme's assets, you can now use Git to inherit directly from the base theme. 
     This has many advantages:
     - Better stability in production.
     - Much easier development workflow--no more "overrides" and maintaining a references directory!
     - Much easier merging in of Core Theme upgrades--you can use Git's existing, famously robust merge tools!
   - To support this new workflow, we've overhauled the Yeoman generator for Mozu themes. **This is the recommended method for creating and upgrading Mozu themes.**
     - Install the new theme generator with `npm install -g yo generator-mozu-theme2`
     - Run it with `yo mozu-theme2`
     - Run it in an empty directory to create a new theme, or an existing theme directory to **upgrade the existing theme in-place to use the new inheritance system!**
* Improvements to the build process:
   - We have removed use of the Bower frontend package manager from the Core theme. The much larger and faster NPM package manager, already in use for build tool dependencies, is now used for frontend dependencies as well. There is a simple script in the Gruntfile which copies dependencies into the `scripts/vendor` directory that Bower used to maintain.
* Numerous bugfixes.
* Other enhancements listed in the [Mozu Release Notes](http://developer.mozu.com/sites/default/files/feeds/learn/article_files/MozuNovember2015ServiceUpdateReleaseNotes.pdf).

## Upgrading to Mozu Core Theme Version 9

You must manually upgrade themes that extend Core4, Core5, Core6, Core7, and Core8 to use Core9 instead. We recommend user acceptance, automated unit, and end-to-end testing of your site to ensure Core9 works for your site.

Use the new [Mozu Theme Generator](http://npmjs.com/package/generator-mozu-theme2) to create new themes **and to update existing themes!**

0. Examine the [merged Pull Requests](pulls?q=is%3Apr+is%3Aclosed+milestone%3Acore9) to see what individual features are coming over from Core.

0. Use the `yo mozu-theme2` command to update your theme to use the new system.

0. Once the generator is complete, you'll have a functioning Git repository that is effectively a "fork" of this one!

0. Your theme will be automatically set to inherit from the last version of the Core theme that it appears to support. You can now upgrade it to use Core9 by simply running `grunt mozutheme:check` to see what versions of Core9 are available, and then merging the appropriate commit. The Grunt task will instruct you in detail.

0. Install your new Core9-based theme on a development sandbox and activate it.

0. Activate Debug Mode in the storefront by adding the query parameter `debugMode=true` to any storefront URL.

0. Visually examine your theme for problems. 

0. Test your site for issues: view a category, search for products, configure a product, manipulate the cart, check out and place an order, make changes to your account page, etc.

0. Make any necessary corrections based on visual errors or console errors.

0. Repeat the last two steps until your theme is free from errors and regressions.
