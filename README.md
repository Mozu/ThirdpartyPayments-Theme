#Pay with Amazon Theme Integration for Mozu Core9#

This repository contains the full source files for the Mozu Core9 theme, with the required changes to enable Pay with Amazon on your Mozu storefront. These theme changes support the Pay with Amazon Application by Mozu. Go to the [Mozu App Marketplace](https://www.mozu.com/marketplace/) to learn more about the app and to request installation on your tenant. 

If you are manually upgrading themes that extend an earlier version of the Mozu Core theme (Core5, Core6, Core7, or Core8), you can upgrade your entire theme from this repo. If you are not ready to upgrade your full theme, the Core8 branch of this repo contains the Pay with Amazon changes for Mozu Core theme version 8. 

**Tip:** Refer to the [Mozu Core Theme](https://github.com/Mozu/core-theme) readme for information about general updates included in Mozu Core9. The branches of the core-theme repo also include readmes for older versions of the Core Theme.

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

##Build this Theme

You can use the [Mozu Theme Generator](https://www.npmjs.com/package/generator-mozu-theme) to update an existing theme to include changes in this repo. You can also run the generator in an empty directory to clone these files as the basis for a brand new theme. 

When you run the Mozu Theme Generator, the tools create a git remote to the Mozu Core9 repository. In the future, if you run the generator from your local theme directory, the tool will automatically check the Mozu Core theme for updates and offer to merge them for you.

###Create a Theme in Mozu Dev Center
1.  In the Dev Center Console, click **Develop > Themes.**
2.  Click **Create Theme**.
3.  Note the **Application Key**.

###Install the Generator
1.  Open a Terminal (OS X) or a Command Prompt (Windows).
2.  Install the Yeoman command-line tool globally: <br/>
`npm install -g yo`
3.  Install the Grunt command-line tool globally: <br/>
`npm install -g grunt-cli`
4.  Install the Mozu Theme Generator globally:<br/>
`npm install -g generator-mozu-theme`

###Run the Generator
1.  Run the Yeoman generator in a directory that contains your theme files. If you are creating a brand new theme, you can run the tool in an empty directory: <br/>
`yo mozu-theme`<br/>
   - **Note:** If you are installing the theme to a non-production Mozu environment, use: <br/> `yo mozu-theme --internal`
<br/>The tool will prompt you to select your environment.
2.  Select **Existing theme from repository**.
3.  Enter the URL for this repository:<br/> `https://github.com/Mozu/PayWithAmazon-Theme`<br/> and hit **Enter**.
4.  Follow the prompts to enter your Dev Center Application Key and login information. The generator runs and creates or merges all the PayWithAmazon-Theme files in your theme directory.
5.  Run `grunt` in your theme directory to upload the theme files to Mozu Dev Center.
6.  View the theme in Dev Center to see your uploaded files and Install the theme to a sandbox. Apply the theme to see the Pay with Amazon button on your Cart and Checkout pages. <br/>
   - **Note:** You must configure Pay with Amazon in your Payment settings in Mozu Admin for the button to appear.

##Additional Resources

* [Pay with Amazon Application by Mozu Configuration Guide](https://www.mozu.com/docs/guides/mozu-apps/pay-with-amazon-app-by-mozu.htm)*
* [Mozu Theme Development Quickstart](https://www.mozu.com/docs/developer/themes/quickstart.htm)
* [Mozu Theme Generator 2.0](https://www.npmjs.com/package/generator-mozu-theme) (npm Package)

**Note:** You must log in with your Mozu Developer Account credentials to access content at [https://www.mozu.com/docs/guides](https://www.mozu.com/docs/guides/guides.htm)
