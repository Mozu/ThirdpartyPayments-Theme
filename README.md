#PayPal Express Theme Integration for Mozu Core9#

This repository contains the full source files for the Mozu Core9 theme, with the required changes to enable PayPal Express on your Mozu storefront. These theme changes support the PayPal Express Application by Mozu. Go to the [Mozu App Marketplace](https://www.mozu.com/marketplace) to learn more about the app and to request installation on your tenant.

If you are manually upgrading themes that extend earlier versions of the Mozu Core theme (Core5, Core6, Core7, or Core8), you can upgrade your entire theme from this repo. If you are not ready to upgrade your full theme, the branches of this repo contain the PayPal Express changes for Mozu Core theme versions 6, 7, and 8. 

**Tip:** Refer to the [Mozu Core Theme](https://github.com/Mozu/core-theme) readme for information about general updates included in Mozu Core9. The branches of the core-theme repo also include readmes for older versions of the Core Theme.

##File Additions and Changes##

**Note:** Use GitHub’s [Compare Changes](https://help.github.com/articles/comparing-commits-across-time/) functionality to see full diffs of the following files.

The PayPal Express Integration adds the following files:
* `scripts/modules/xpressPaypal.js`

And edits the following files:
* `scripts/modules/models-checkout.js`
* `scripts/pages/checkout.js`
* `scripts/pages/cart.js`
* `stylesheets/modules/common/form-step.less`
* `templates/back-office/packing-slip.hypr`
* `templates/email/order-confirmation.hypr`
* `templates/email/order-refund-issued.hypr`
* `templates/modules/cart/cart-table.hypr.live`
* `templates/modules/checkout/checkout-payment.hypr.live`
* `templates/modules/checkout/payment-selector.hypr.live`
* `templates/modules/checkout/step-payment-info.hypr.live`
* `templates/modules/checkout/step-shipping-address.hypr.live`
* `templates/modules/common/email-address-summary.hypr.live`
* `templates/modules/web-fonts-loader.hypr`
* `theme.json`

##Build this Theme

You can use the [Mozu Theme Generator](https://www.npmjs.com/package/generator-mozu-theme) to update an existing theme to include changes in this repo. You can also run the generator in an empty directory to clone these files as the basis for a brand new theme. 

When you run the Mozu Theme Generator, the tools create a git remote to the Mozu [core-theme](https://github.com/Mozu/core-theme/tree/master) repository. In the future, if you run the generator from your local theme directory, the tool will automatically check the Mozu Core theme for updates and offer to merge them for you.

###Create a Theme in Mozu Dev Center
1.	In the Dev Center Console, click **Develop > Themes.**
2.	Click **Create Theme**.
3.	Note the **Application Key**.

###Install the Generator
1.	Open a Terminal (OS X) or a Command Prompt (Windows).
2.	Install the Yeoman command-line tool globally: <br/>
`npm install -g yo`
3.	Install the Grunt command-line tool globally: <br/>
`npm install -g grunt-cli`
4.	Install the Mozu Theme Generator globally:<br/>
`npm install -g generator-mozu-theme`

###Run the Generator
1.	Run the Yeoman generator in a directory that contains your theme files. If you are creating a brand new theme, you can run the generator in an empty directory: <br/>
`yo mozu-theme`<br/>
   - **Note:** If you are installing the theme to a non-production Mozu environment, use: <br/> `yo mozu-theme --internal`
<br/>The tool will prompt you to select your environment.
2.	Select **Existing theme from repository**.
3.	Enter the URL for this repository:<br/> `https://github.com/Mozu/PayPalExpress-Theme`<br/> and hit **Enter**.
4.	Follow the prompts to enter your Dev Center Application Key and login information. The generator runs and creates or merges all the PayPalExpress-Theme files in your theme directory.
5.	Run `grunt` in your theme directory to upload the theme files to Mozu Dev Center.
6.	View the theme in Dev Center to see your uploaded files and Install the theme to a sandbox. Apply the theme to see the **Check out with PayPal** button on your Cart and Checkout pages. <br/>
   - **Note:** You must configure PayPal Express in your Payment settings in Mozu Admin for the button to appear.


##Additional Resources
* [PayPal Express Application by Mozu Configuration Guide](https://www.mozu.com/docs/guides/mozu-apps/paypal-express-app-by-mozu.htm)*
* [Introduction to Mozu Themes](https://www.mozu.com/docs/developer/themes/introduction.htm)
* [Comparing commits across time](https://help.github.com/articles/comparing-commits-across-time/) (GitHub Help) 

**Note:** You must log in with your Mozu Developer Account credentials to access content at [https://www.mozu.com/docs/guides](https://www.mozu.com/docs/guides/guides.htm)

