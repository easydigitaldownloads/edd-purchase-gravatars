=== EDD Purchase Gravatars ===
Contributors: easydigitaldownloads, sumobi, cklosows
Tags: easy digital downloads, digital downloads, e-downloads, edd, sumobi, purchase, gravatars, e-commerce
Requires at least: 3.3
Tested up to: 4.9
Stable tag: 1.0.4
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Displays Gravatars of customers who have purchased your product

== Description ==

This plugin requires [Easy Digital Downloads](https://wordpress.org/plugins/easy-digital-downloads/ "Easy Digital Downloads"). It outputs gravatars of all the customers who have purchased your product.

It works by using the customer's email that they used to purchase your product, and checking it against Gravatar.com. Only unique email addresses are used, so if a customer purchases your product more than once, it will only show their Gravatar once.

To show the Gravatars of customers who have purchased your product, use the [edd_purchase_gravatars] shortcode, or drag the provided widget into the sidebar of your single download page. You can also show the gravatars of a particular product anywhere on your website using the template tag or shortcode, by passing in the download's ID.

**Features**

1. Set a heading to display above the Gravatars.
1. Set the size of each Gravatar (512px maximum)
1. Set the minimum number of unique purchases a download must have before the Gravatars are shown. Leave blank for no minimum.
1. Set the maximum number of gravatars to show. Leave blank for no limit.
1. Only show customers with a Gravatar account
1. Randomize the Gravatars


**Shortcode usage**

To show the purchase gravatars on a single download, add this shortcode into the WP editor:

    [edd_purchase_gravatars]

To show the purchase gravatars of a particular download on another page or download, add the id parameter. This example will show the download with an ID of 942.

    [edd_purchase_gravatars id="942"]

To show the purchase gravatars with a custom title, use the title parameter. This will override the heading in the main plugin options

    [edd_purchase_gravatars title="This is my custom title"]

**Template Tag usage**

This example will show the purchase gravatars of whichever single download it is placed on.

    $gravatars = new EDD_Purchase_Gravatars();
    echo $gravatars->gravatars( get_the_ID() );

If you'd like to show purchase gravatars of a specific download from somewhere else on your site, pass in the ID of the download like so:

	$gravatars = new EDD_Purchase_Gravatars();
    echo $gravatars->gravatars( '942' );

To show a custom title, pass in your title as the 2nd parameter

    $gravatars = new EDD_Purchase_Gravatars();
    echo $gravatars->gravatars( get_the_ID(), 'This is my custom title' );

**Widget usage**

Drag the widget into your sidebar. If the widget is shown on a single download page, and that download has purchases, the purchase gravatars will be shown.

== Installation ==

1. Unpack the entire contents of this plugin zip file into your `wp-content/plugins/` folder locally
1. Upload to your site
1. Navigate to `wp-admin/plugins.php` on your site (your WP Admin plugin page)
1. Activate this plugin
1. Configure the plugin's settings from downloads -> settings -> extensions
1. Use the included shortcode, template tag or widget.

OR you can just install it with WordPress by going to Plugins >> Add New >> and type this plugin's name


== Frequently Asked Questions ==

= My Gravatars are not showing =

In order for the gravatars to display, "Show Avatars" must be enabled in Settings -> Discussion.

= How can I change the default avatar? =

The default avatar can be changed from Settings -> Discussion. If you are a developer, there's a edd_pg_gravatar_default_image filter available to pass in any image URL.

== Screenshots ==

1. Using the [edd_purchase_gravatars] shortcode
1. Using the widget in a theme's sidebar
1. The settings screen in Easy Digital Download's extension tab
1. The widget

== Changelog ==

= 1.0.4 =
* Tweak: Moved extension settings to own "Purchase Gravatars" section

= 1.0.3 =
* Fix: PHP 7+ compatibility with widget constructor method name.

= 1.0.2 =
* Fix: Use EDD_Payment for customer information to avoid nested calls to maybe_unserialize.

= 1.0.1 =
* New: Added edd_pg_name filter for the image's alt tag
* New: French translations, props fxbenard
* Fix: Removed PHP 4 style constructors

= 1.0 =
* Initial release
