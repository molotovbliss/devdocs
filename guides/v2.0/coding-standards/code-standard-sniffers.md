---
layout: default
group: coding-standards
subgroup: Coding standards
title: Code sniffers
menu_title: PHP code sniffers
menu_order: 3
version: 2.0
github_link: coding-standards/code-standard-sniffers.md
---

## PHP code sniffers

We recommend the consistent use of a <i>code sniffer</i> to enhance the readability of your code and help ensure that it meets Magento code standards.  A code sniffer is a tool that automates the process of identifying code irregularities. Although a sniffer will identify many more inconsistencies and errors than a manual edit, we recommend that you evaluate and make any fixes that your sniffer program identifies.  

Magento recommends the use of [PHP_CodeSniffer](http://pear.php.net/manual/en/package.php.php-codesniffer.faq.php){:target="_blank"}, the most popular code sniffer in use throughout the PHP development community.
PHP_CodeSniffer 1.4.0+ includes PSR-1 and PSR-2 standards, which are followed by Magento 2. 
You can configure PHP_CodeSniffer to use your own rules, too. The [Magento Extension Quality Program Coding Standard](https://github.com/magento/marketplace-eqp){:target="_blank"} provides specifications that you can use to configure your code sniffer of choice to bring your _PHP coding style closer to Magento PHP standards_.



### Code standards 

Magento supports the [PSR-1](http://www.php-fig.org/psr/psr-1/){:target="_blank"} and [PSR-2](http://www.php-fig.org/psr/psr-2/){:target="_blank"} standards. 


The [Coding standards overview](http://devdocs.magento.com/guides/v2.0/coding-standards/bk-coding-standards.html){:target="_blank"} introduces Magento-specific practices for PHP, JavaScript, and JQuery. 
