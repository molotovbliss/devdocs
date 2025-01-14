---
layout: default
group: release-notes
subgroup: 02_rel-notes
title: Magento EE 2.0.12 Release Notes
menu_title: Magento EE 2.0.12 Release Notes
menu_order: 267
version: 2.0
level3_menu_node: level3child
level3_subgroup: ee20-relnotes 
github_link: release-notes/ReleaseNotes2.0.12EE.md
---

We are pleased to present Magento Enterprise Edition 2.0.12. This release includes many functional fixes and enhancements. 

Looking for the <a href="http://devdocs.magento.com/guides/v2.0/cloud/release-notes/CloudReleaseNotes2.1.4.html" target="_blank">Magento Enterprise Cloud Edition 2.1.4 and 2.0.12 Release Notes</a>?


## Highlights

Magento 2.0.12 contains more than 20 functional fixes and enhancements, and one security enhancement. Look for the following highlights in this release:

* **Removal of vulnerability with the Zend framework `Zend_Mail` library**. For more information, see <a href="https://magento.com/security/news/new-zend-framework-1-security-vulnerability" target="_blank">New Zend Framework 1 Security Vulnerability</a>.  


* **Updates to the catalog, payment, and sales modules**

## Security enhancement

This release includes an important enhancement to the security of your Magento software. While there are no confirmed attacks related to the Zend framework `Zend_Mail` library vulnerability to date, certain vulnerabilities can potentially be exploited to access customer information or take over administrator sessions. We recommend that you upgrade your existing Magento software to the latest version as soon as possible.


## Functional fixes

We address the following functional issues in this release.


### Catalog

<!--- 58504 -->* You can now directly add a configurable product (with all possible options defined) to your shopping cart from the category page. Previously,  you had to review a product on the product page before completing the process of adding it to your shopping cart. <a href="https://github.com/magento/magento2/issues/2574" target="_blank">(GITHUB-2574)</a>, <a href="https://github.com/magento/magento2/issues/5850" target="_blank">(GITHUB-5850)</a>, <a href="https://github.com/magento/magento2/issues/5882" target="_blank">(GITHUB-5882)</a>, <a href="https://github.com/magento/magento2/issues/6572" target="_blank">(GITHUB-6572)</a>,  <a href="https://github.com/magento/magento2/issues/5558" target="_blank">(GITHUB-5558)</a>

<!--- 60055 -->* Admin users can no longer create an empty URL key for a category. Previously, Magento let Admin users create an empty URL key, which lead to category-related errors.

<!--- 62647 -->* Magento now successfully saves a product even when you include an empty Custom Options row (**Products > Catalog > Custom Options**). Previously, under these conditions, Magento displayed the `Invalid option value` error message, and did not save the product.  

<!--- 61628 -->* The **Match products by rule** option in the Admin interface now works as expected. 

<!--- 62654 -->* You can now successfully match products by rule with an AND condition on Category Rule. Previously, this operation did not return any matched products.  



### Checkout

<!--- 58946 -->* Magento now displays custom address attributes on the checkout summary. 

<!--- 60877 -->* The **Use Default Checkboxes for Custom Options** option now works as expected. Previously, the checkboxes under the option title and value title were not rendered correctly, and the feature did not work.


<!--- 61113 -->* Magento now displays the **Thank you for your purchase!** message after a customer successfully checks out. Previously,  Magento did not display this message, even though the HTML code was present. <a href="https://github.com/magento/magento2/issues/6968" target="_blank">(GITHUB-6968)</a>

<!--- 61022 -->* You can now create a new order from the Magento Admin. <a href="https://github.com/magento/magento2/issues/5533" target="_blank">(GITHUB-5533)</a>,  <a href="https://github.com/magento/magento2/issues/6855" target="_blank">(GITHUB-6855)</a>



### Customer


<!--- 60965 -->* When you add an address, new custom attributes are now displayed together, along with other address details. 



### Gift card

<!--- 57610 -->* You can now use a gift card to complete payment for an order that contains gift wrap. Previously, when you paid for an order with a gift card, the gift wrap amount remained as a balance, even when the gift card contained sufficient funds to cover the expense of gift wrapping.




### Import/export

<!--- 61264 -->* Magento can now import `additional_images` that are tagged with labels that contain a comma separator.

<!--- 61075 -->* Magento no longer deletes a product after you select the Replace option while importing a product. Previously,  Magento deleted the product rather than replacing it.  

<!--- 63243 -->* You can now use Extension Manager to uninstall extensions that were installed using Composer. 



### Miscellaneous


<!--- 60724 -->* Magento now redirects you to the Setup page as expected when you specify a particular port when installing the application using Nginx. Previously, Magento did not redirect you to the Setup page, and instead displayed this message in `var/report`: `You cannot install Magento using the Setup Wizard because the Magento setup directory cannot be accessed`. 

<!--- 57519 -->* Requests to Edge Side Includes (ESI) now return data. Previously, requests to ESI did not return data because the requested block was absent in the layout. 

<!--- 62680 -->* Admin users need view permission to the store to which the customers belong in order to see information about those customers. Previously, an Admin user could see information about customers that belonged to websites or stores for which the user did not have explicit permission to view.

<!--- 63209 -->* You can now change a category's display mode to Static Block Only when the flat indexer is on. Previously, Magento experienced a fatal error under these conditions.

<!--- 61188 -->* You can now use Composer to install Magento 2.0.x with sample data, and use `deploy:mode:set production`, without incurring an error. Previously, Magento displayed this error when you tried to use `deploy:mode:set production` under these conditions: 

		Start compilation
		Command returned non-zero exit code:
		`php -f /var/www/html/20ce/bin/magento setup:di:compile-multi-tenant 2>&1`



### Payment methods

<!--- 56925 -->* You can now ship items to a country from which you have not authorized payment. Previously, when a customer tried to ship an order to a country from which the store was not authorized to receive payment, Magento displays this message, **No Payment method available**.



### Sales


<!--- 61151 -->* Magento now displays an error message as expected when a user tries to add less than the specified minimum quantity of a product to his shopping cart. 

<!--- 61091 -->* The Free Shipping method now shows up as an available option when you create an order from the Magento Admin. <a href="https://github.com/magento/magento2/issues/2939" target="_blank">(GITHUB-2939)</a>

<!--- 60327 -->* Magento no longer assigns all orders a status of Suspected Fraud in multi-currency store configurations. <a href="https://github.com/magento/magento2/issues/4263" target="_blank">(GITHUB-4263)</a>

<!--- 61146 -->* An Admin user with restricted permissions no longer has access to all orders. 




### Travis builds

<!--- 62455 -->* We’ve fixed a fatal issue that occurred if you ran Travis builds on `imagettfbbox 2.1.2`. Previously, you’d receive this error: `PHP Fatal error: Call to undefined function Magento\Framework\Image\Adapter\imagettfbbox() in /home/travis/build/magento/magento2/lib/internal/Magento/Framework/Image/Adapter/Gd2.php`.


<!--- NOT A BUG --> 

<!--- 62727 --> 

<!--- 62795 -->


<!--- INTERNAL ONLY --> 


<!--- 62121 -->

<!--- 61258 -->


<!--- 62201 -->
<!--- 62202 -->
<!--- 61079 -->



<!--- CANNOT REPRODUCE --> 

<!--- 61148 -->

<!--- 62793 --> 

<!--- 62581 --> 

<!--- 62574 --> 

<!--- 62671 --> 

## Known issues

<!--- 62661 -->* **Issue**: You cannot cancel check out of an order you are making with the Worldpay payment option without emptying your shopping cart. Currently, when you cancel a checkout operation while using this payment method, Magento empties your shopping cart.

<!--- 61112 -->* **Issue**: Customers cannot view all images that are associated with a configurable product. The gallery does not show all the images that are associated with a configurable option. <a href="https://github.com/magento/magento2/issues/6195" target="_blank">(GITHUB-6195)</a>, <a href="https://github.com/magento/magento2/issues/4101" target="_blank">(GITHUB-4101)</a>

<!--- 61708 -->* **Issue**: You cannot use the Web Setup wizard to uninstall a module. 


<!--- 61960 -->* **Issue**: Magento does not save a configurable product with specific attribute options under the following conditions: 

	* the configurable product price is derived from its children
	* the children have been previously created and are in stock


<!--- 57165 -->* **Issue**: After you’ve removed all variations of a configurable product (**Admin > Configuration > Remove Product**), the **Add Products Manually** link is not available. **Workaround**: Retain at least one variation or use the **Choose a different product option** option.

<!--- 61970 -->* **Issue**:  Magento saves images and videos as global values, not per store view. This can potentially result in the unwanted duplication of product images across store views. 

<!--- 61208 -->* **Issue**: Magento does not consistently save video information for a product after you edit the information. 

<!--- 61100 -->* **Issue**: Client-side LESS compilation is not working properly. Consequently, page load performance is not optimal.

<!--- 61241 -->* **Issue**: You encounter an error when you try to install Magento with the `magento/module-cms-sample-data 100.0.5` sample data set: **Error in update!** 

<!--- 62049 -->* **Issue**: Magento does not always display the accurate price for a configurable product when running Magento in an environment that contains multiple store views and websites. 

<!--- 61279 -->* **Issue**: You cannot use Braintree PayPal to successfully complete the purchase of a gift card. Instead, your purchase stays in the processing stage.

<!--- 63212 -->* **Issue**: You cannot successfully create and save a dropdown attribute using **Stores > Attributes > Product > Add New Attribute**. **Workaround**: Save the attribute with **values required** set to **no** first, before re-saving it with **values required** set to **yes**.

<!--- 61238 -->* **Issue**: Magento experiences a fatal error when you try to get a refund on an invoice. (Specifically, a fatal error occurs when calling `LocalizedException` in `CreditmemoService`.)

<!--- 62131 -->* **Issue**: Search synonyms not working as expected. Typically, Magento redirects users to the URL set in the search term. Currently, Magento ignores the synonym, and searches for the term that  the customer enters. 

<!--- 61973 -->* **Issue**: Magento does not enforce the value that specifies the minimum quantity of a product that a customer can add to the shopping cart. Instead of displaying a message that prompts the user to enter the required minimum, Magento permits a customer to order as few items as they’d like. 

<!--- 61150 -->* **Issue**: When editing a product description, you cannot delete a product image across multiple stores. When you try to save your edits, Magento displays this message: **The image cannot be removed as it has been assigned to the other image role**. 





## System requirements
Our technology stack is built on PHP and MySQL. See
<a href="{{ page.baseurl }}install-gde/system-requirements.html" target="_blank">System Requirements</a>.


{% include install/releasenotes/ee_install_20.md %}



## Migration toolkits
The <a href="{{ page.baseurl }}migration/migration-migrate.html" target="_blank">Data Migration Tool</a> helps transfer existing Magento 1.x store data to Magento 2.x. This command-line interface includes verification, progress tracking, logging, and testing functions. For installation instructions, see  <a href="{{ page.baseurl }}migration/migration-tool-install.html" target="_blank">Install the Data Migration Tool</a>. Consider exploring or contributing to the <a href="https://github.com/magento/data-migration-tool" target="_blank"> Magento Data Migration repository</a>.

The <a href="https://github.com/magento/code-migration" target="_blank">Code Migration Toolkit</a> helps transfer existing Magento 1.x store extensions and customizations to Magento 2.0.x. The command-line interface includes scripts for converting Magento 1.x modules and layouts.

## Credits

Dear community members, thank you for your suggestions and bug reports.
