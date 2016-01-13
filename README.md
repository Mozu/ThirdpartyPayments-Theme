#PayPal Express Theme Integration for Mozu Core9#

This repository contains the full source files for the Mozu Core9 theme, with the required changes to enable PayPal Express on your Mozu storefront. These theme changes support the PayPal Express Application by Mozu. Go to the [Mozu App Marketplace](https://www.mozu.com/marketplace) to learn more about the app and to request installation on your tenant.

If you are manually upgrading themes that extend earlier versions of the Mozu Core theme (Core5, Core6, Core7, or Core8), you can upgrade your entire theme from this repo. If you are not ready to upgrade your full theme, the branches of this repo contain the PayPal Express changes for Mozu Core theme versions 6, 7, and 8. 

For your convenience, the full readme for Mozu Core Theme Version 9 is included at the bottom of this file.

##File Additions and Changes##

**Note:** Use GitHub’s [Compare Changes](https://help.github.com/articles/comparing-commits-across-time/) functionality to see full diffs of the following files.

The PayPal Express Integration adds the following files:
* `scripts/modules/xpressPaypal.js`

And edits the following files:
* `scripts/modules/models-checkout.js`
* `scripts/pages/checkout.js`
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

You can use the [Mozu Theme Generator](https://www.npmjs.com/package/generator-mozu-theme) to update an existing theme to include changes in this repo. The generator can also create a brand new theme with this theme as the base. When you run the Mozu Theme Generator, the tool creates a git remote to this repository. In the future, if you run the generator from your theme repository, the tool will automatically check this repo for any updates and offer to merge them for you.

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
1.	Run the Yeoman generator in a directory that contains your theme files. If you are creating a brand new theme, you can run the tool in an empty directory: <br/>
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
* [PayPal Express Configuration Guide](http://mozu.github.io/IntegrationDocuments/PayPalExpress/Mozu-PayPalExpress-App.htm) (App Documentation)
* [Mozu Theme Development Quickstart](http://developer.mozu.com/content/learn/themedev/quickstart/create-your-first-theme.htm) (Mozu Documentation)
* [Mozu Theme Generator 2.0](https://www.npmjs.com/package/generator-mozu-theme) (npm Package)
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
     - Install the new theme generator with `npm install -g yo generator-mozu-theme`
     - Run it with `yo mozu-theme`
     - Run it in an empty directory to create a new theme, or an existing theme directory to **upgrade the existing theme in-place to use the new inheritance system!**
* Improvements to the build process:
   - We have removed use of the Bower frontend package manager from the Core theme. The much larger and faster NPM package manager, already in use for build tool dependencies, is now used for frontend dependencies as well. There is a simple script in the Gruntfile which copies dependencies into the `scripts/vendor` directory that Bower used to maintain.
* Numerous bugfixes.
* Other enhancements listed in the [Mozu Release Notes](http://developer.mozu.com/sites/default/files/feeds/learn/article_files/MozuNovember2015ServiceUpdateReleaseNotes.pdf).

## Upgrading to Mozu Core Theme Version 9

You must manually upgrade themes that extend Core4, Core5, Core6, Core7, and Core8 to use Core9 instead. We recommend user acceptance, automated unit, and end-to-end testing of your site to ensure Core9 works for your site.

Use the new [Mozu Theme Generator](http://npmjs.com/package/generator-mozu-theme) to create new themes **and to update existing themes!**

0. Examine the [merged Pull Requests](pulls?q=is%3Apr+is%3Aclosed+milestone%3Acore9) to see what individual features are coming over from Core.

0. Use the `yo mozu-theme` command to update your theme to use the new system.

0. Once the generator is complete, you'll have a functioning Git repository that is effectively a "fork" of this one!

0. Your theme will be automatically set to inherit from the last version of the Core theme that it appears to support. You can now upgrade it to use Core9 by simply running `grunt mozutheme:check` to see what versions of Core9 are available, and then merging the appropriate commit. The Grunt task will instruct you in detail.

0. Install your new Core9-based theme on a development sandbox and activate it.

0. Activate Debug Mode in the storefront by adding the query parameter `debugMode=true` to any storefront URL.

0. Visually examine your theme for problems. 

0. Test your site for issues: view a category, search for products, configure a product, manipulate the cart, check out and place an order, make changes to your account page, etc.

0. Make any necessary corrections based on visual errors or console errors.

0. Repeat the last two steps until your theme is free from errors and regressions.
