=== Really Simple SSL ===

Contributors: RogierLankhorst, markwolters

Donate link: https://www.paypal.me/reallysimplessl

Tags: SSL, https, force SSL, mixed content, insecure content, secure website, website security, TLS, security, secure socket layers, HSTS

Requires at least: 4.2
License: GPL2
Tested up to: 5.0
Requires PHP: 5.4
Stable tag: 3.1.3

No setup required! You only need an SSL certificate, and this plugin will do the rest.

== Description ==
Really Simple SSL automatically detects your settings and configures your website to run over https.
To keep it lightweight, the options are kept to a minimum. The entire site will move to SSL.

= Three simple steps for setup: =
* Get an SSL certificate (can't do that for you, sorry).
* Activate this plugin
* Enable SSL with one click

Always backup before you go! If you do not have a sound backup policy, start having one! See [our recommendations](https://really-simple-ssl.com/knowledge-base/backing-up-your-site/).

Really Simple SSL is ClassicPress compatible. Any code suggestions? We're on [GitHub](https://github.com/rlankhorst/really-simple-ssl) as well!

= Love Really Simple SSL? =
Hopefully this plugin save you some hours of work. If you want to support the continuing development of this plugin, you might consider buying the [premium](https://www.really-simple-ssl.com/pro/), which includes
some cool features.
= Pro features =
* The mixed content scan, which shows you what you have to do if you don't have the green lock yet
* The option to enable HTTP Strict Transport Security
* The option to configure your site for the HSTS preload list
* Mixed Content Fixer for the back-end
* More detailed feedback on the configuration page.
* Certificate expiration check: get an email when your SSL certificate is about to expire.
* Premium support

= What does the plugin actually do =
* The plugin handles most issues that WordPress has with SSL, like when you're behind a reverse proxy/loadbalancer, or when no headers are passed which WordPress can use to detect SSL.
* All incoming requests are redirected to https. Default with an internal WordPress redirect, but you can also enable a .htaccess redirect.
* The site url and home url are changed to https.
* Your insecure content is fixed by replacing all http:// urls with https://, except hyperlinks to other domains. Dynamically, so no database changes are made (except for the siteurl and homeurl).

[contact](https://www.really-simple-ssl.com/contact/) me if you have any questions, issues, or suggestions. Really Simple SSL is developed by [Really Simple Plugins](https://www.really-simple-plugins.com).

= Like to have this plugin in your language? =
Translations can be added very easily [here](https://translate.wordpress.org/projects/wp-plugins/really-simple-ssl). If you do, I can get you added as translation editor to approve the translations.

== Installation ==
To install this plugin:

1. Make a backup!
2. Install your SSL certificate
3. Download the plugin
4. Upload the plugin to the wp-content/plugins directory,
5. Go to “plugins” in your WordPress admin, then click activate.
6. You will now see a notice asking you to enable SSL. Click it and log in again.

== Frequently Asked Questions ==

= Knowledge base =
For more detailed explanations and documentation on redirect loops, deactivating, mixed content, errors, and so on, please search the [documentation](https://www.really-simple-ssl.com/knowledge-base/)

= Does the mixed content fixer make my site slower? =
On a site where the source consists of about 60.000 characters, the delay caused by the mixed content fixer is about 0.00188 seconds. If this is too much for you, fix the mixed content manually and deactivate it in the settings.

= Uninstalling Really Simple SSL =
The plugin checks your certificate before enabling, but if, for example, you migrated the site to a non-ssl environment, you might get locked out of the back-end.
If you can't deactivate, do not just remove the plugin folder to uninstall! Follow these [instructions](https://really-simple-ssl.com/knowledge-base/uninstall-websitebackend-not-accessible/).

= Mixed content issues =
Most mixed content issues are caused by urls in css or js files.
For detailed instructions on how to find mixed content read this [article](https://really-simple-ssl.com/knowledge-base/how-to-track-down-mixed-content-or-insecure-content/).

= Redirect loop issues =
If you are experiencing redirect loops on your site, try these [instructions](https://really-simple-ssl.com/knowledge-base/my-website-is-in-a-redirect-loop/).

= Is the plugin multisite compatible? =
Yes. There is a dedicated network settings page where you can switch between network activated SSL and per page SSL. In the dedicated pro for multisite plugin, you can override all site settings for SSL on the network level, and can activate and deactivate SSL in the network menu for each site.

== Changelog ==
= 3.1.3 =
* Tweak: no longer shows notices on Gutenberg edit screens
* Tweak: updated Google Analytics with link to SSL settings page
* Fix: multisite blog count now only counts public sites

= 3.1.2 =
* Tweak: added cool checkboxes
* Tweak: .well-known/acme-challenge/ is excluded from .htaccess https:// redirect
* Tweak: implemented transients for functions that use curl/wp_remote_get()
* Tweak: improved mixed content fixer detection notifications
* Tweak: removed review notice for multisite

= 3.1.1 =
* Fix: Multisite network wide activation/deactivation cron not saving settings because user capability not set this early in the process.

= 3.1 =
* Fix: fixed a bug in certificate detection
* Tweak: added HTTP_X_PROTO as supported header
* Tweak: split HTTP_X_FORWARDED_SSL into a variation which can be either '1' or 'on'
* Tweak: improved certificate detection by stripping domains of subfolders.
* Tweak: Multisite bulk SSL activation now chunked in 200 site blocks, to prevent time out issues on large multisite networks.
* Tweak: a 'leave review' notice for new free users

= 3.0.5 =
* Fix: untranslatable string made translatable.

= 3.0.4 =
* Fix: removed anonymous function to maintain PHP 5.2 compatibility.

= 3.0.3 =
* Tweak: mixed content fixer will no longer fire on XML content
* Tweak: network menu on subsites now always shows to Super Admins
* Tweak: flush rewrite rules upon activation is delayed by one minute to reduce server load

= 3.0.2 =
* Fix: fixed an image containing uppercase characters, which can lead to the image not showing on some servers.
* Fix: fixed an issue where the 'data-rsssl=1' marker wasn't inserted when the <body> tag was empty.

= 3.0.1 =
* Tweak: Add privacy notice
* Tweak: Set javascript redirect to false by default
* Fix: Hide SSL notice on multisite for all subsites, and show only for "activate_plugins" cap users

= 3.0 =
* Added a built-in certificate check in the class-certificate.php file that checks if the domain is present in the common names and/or the alternative names section.
* The .htaccess redirect now uses $1 instead of {REQUEST_URI}.
* Added an option to deactivate the plugin while keeping SSL in the SSL settings.
* Added a filter for the Javascript redirect.
* Added a sidebar with recommended plugins.

= 2.5.26 =
* Fix: multisite menu not showing when main site is not SSL.
* Fix: the admin_url and site_url filter get an empty blog_id when checking the URL for the current blog.
* Tweak: added comment to encourage backing up to activation notice.
* Tested the plugin with Gutenberg.

= 2.5.25 =
* Fix: "switch mixed content fixer hook" option not visible on the multisites settings page
* Tweak: several typo's and uppercasing

= 2.5.24 =
* Fix: On multisite, admin_url forced current blog URL's over http even when the current blog was loaded over https. This will now only force http for other blog_urls than the current one, when they are on http and not https.

= 2.5.23 =
* Tested up to WP 4.9
* Added secure cookie notice

= 2.5.22 =
* Changed mixed content fixer hook back from wp_print_footer_scripts to shutdown

= 2.5.21 =
* Fixed double slash in paths to files
* Fixed typo in activation notice.
* Tweak: added option to not flush the rewrite rules
* Fix: prevent forcing admin_url to http when FORCE_SSL_ADMIN is defined

= 2.5.20 =
* Tweak: constant RSSSL_DISMISS_ACTIVATE_SSL_NOTICE to allow users to hide notices.
* Tweak: setting to switch the mixed content fixer hook from template_redirect to init.
* Fix: nag in multisite didn't dismiss properly

= 2.5.19 =
* Multisite fix: due to a merge admin_url and site_url filters were dropped, re-added them
* Added constant RSSSL_CONTENT_FIXER_ON_INIT so users can keep on using the init hook for the mixed content fixer.

= 2.5.18 =
* Tweak: Removed JetPack fix, as it is now incorporated in JetPack.
* Tweak: Moved mixed content fixer hook to template_redirect
* Fix: Changed flush rewrite rules hook from admin_init to shutdown, on activation of SSL.
* Multisite fix: Changed function which checks if admin_url and site_url should return http or https to check for https in home_url.
* Tweak: Explicitly excluded json and xmlrpc requests from the mixed content fixer

= 2.5.17 =
* Tweak: Added a function where the home_url and site_url on multisite check if it should be http or https when SSL is enabled on a per site basis.
* Tweak: Added a notice that there will be no network menu when Really Simple SSL is activated per site.
* Tweak: Added hook for new multisite site so a new site will be activated as SSL when network wide is activated.
* Tweak: limited the JetPack listen on port 80 tweak to reverse proxy servers.
* Tweak: created a dedicated rest api redirect constant in case users want to prevent the rest api from redirecting to https.
* Fix: dismissal of SSL activated notice on multisite did not work properly

= 2.5.16 =
* Reverted wp_safe_redirect to wp_redirect, as wp_safe_redirect causes a redirect to wp-login.php even when the primary url is domain.com and request url www.domain.com

= 2.5.15 =
* No functional changes, version change because WordPress was not processing the version update

= 2.5.14 =
* Fix: fixed issue in the mixed content fixer where on optimized html the match would match across elements.
* replaced wp_redirect with wp_safe_redirect
* Added force SSL on wp_rest_api

= 2.5.13 =
* Tweak: configuration more function

= 2.5.12 =
* Added multisite settings page
* Added filter for .htaccess code output
* Increased user capability to "activate_plugins"
* Added SSL_FORWARDED_PROTO = 1 in addition to SSL_FORWARDED_PROTO = on as supported SSL recognition variable.

= 2.5.11 =
* Removed curl in favor of wp_remote_get

= 2.5.10 =
* Fastest cache compatibility fix

= 2.5.9 =
* Multisite tweaks

= 2.5.8 =
* Removed automatic insertion of .htaccess redirects. The .htaccess redirects work fine for most people, but can cause issues in some edge cases.
* Added option to explicitly insert .htaccess redirect
* Added safe mode constant RSSSL_SAFE_MODE to enable activating in a minimized way
* Fix: RLRSSSL_DO_NOT_EDIT_HTACCESS constant did not override setting correctly when setting was used before.
* Dropped cache flushing on activation, as this does not always work as expected

= 2.5.7 =
* Tweak: changes testurl to the function test_url()

= 2.5.6 =
* version nr fix

= 2.5.5 =
* Reverted some changes to 2.4.3, as it was causing issues for some users.

= 2.5.4 =
fix: Adjusted selection order of .htaccess rules, preventing redirect loops

= 2.5.3 =
* Changed .htaccess redirects to use only one condition

= 2.5.2 =
* removed file_get_contents function from class_url.php, as in some cases this causes issues.

= 2.5.1 =
* Added help tooltips
* Fix: typos in explanations
* Added detected server to debug Log
* Added test folder for CloudFlare
* Added htaccess redirect to use all available server vars for checking SSL.

= 2.5.0 =
* Tweak: Improved support for cloudflare
* Tweak: Added support for Cloudfront, thanks to Sharif Alexandre
* Fix: Prevent writing of empty .htaccess redirect
* Tweak: Added option for 301 internal wp redirect
* Tweak: Improved NGINX support
* Tweak: Added support for when only the $_ENV[HTTPS] variable is present
* Fix: Mixed content fixing of escaped URLS

= 2.4.3 =
* Removed banner in admin

= 2.4.2 =
* Tweak: Added reload over https link for when SSL was not detected
* Fixed: After reloading page when the .htaccess message shows, .htaccess is now rewritten.
* Tweak: Removed Yoast notices
* Tested for WP 4.7
* Fixed: bug where network options were not removed properly on deactivation
* Tweak: Changed mixed content marker to variation without quotes, to prevent issues with scripting etc.

= 2.4.1 =
* Tweak: improved HSTS check

= 2.4.0 =
* Fixed: added a version check on wp_get_sites / get_sites to get rid of deprecated function notice, and keep backward compatibility.
* Fixed: A bug in multisite where plugin_url returned a malformed url in case of main site containing a trailing slash, and subsite not. Thanks to @gahapati for reporting this bug.
* Tweak: Added button to settings page to enable SSL, for cases where another plugin is blocking admin notices.
* Tweak: Rebuilt the mixed content fixer, for better compatibility
* Tweak: Improved the mixed content marker on the front-end, so it's less noticeable, and won't get removed by minification code.

= 2.3.14 =
* Fixed: Clearing of WP Rocket cache after SSL activation causing an error
* Fixed: Clearing of W3TC after SSL activation did not function properly

= 2.3.13 =
* Re-inserted Jetpack fix.

= 2.3.12 =
* Requires at least changed back to 4.2, as the function that this was meant for didn’t make it in current release yet.

= 2.3.11 =
* Improved request method in url class
* Added check if .htaccess actually exists in htaccess_contains_redirect_rules()
* Made activation message more clear.

= 2.3.10 =
* Tested for 4.6
* Tweak: changed check for htaccess redirect from checking the RSSSL comments to checking the redirect rule itself
* Fix: htaccess not writable message not shown anymore when SSL not yet enabled
* Tweak: extended mixed content fixer to cover actions in forms, as those should also be http in case of external urls.
* Tweak: added safe domain list for domains that get found but are no threat.
* Tweak: added filter for get_admin_url in multisite situations, where WP always returns an https url, although the site might not be on SSL
* Tweak: htaccess files and wpconfig are rewritten when the settings page is loaded

= 2.3.9 =
* Fix: removed internal WordPress redirect as it causes issues for some users.
* Tweak: improved url request method

= 2.3.8 =
* Tweak: Fallback redirect changed into internal wp redirect, which is faster
* Tweak: When no .htaccess rules are detected, redirect option is enabled automatically
* Tweak: Url request falls back to file_get_contents when curl does not give a result

= 2.3.7 =
* Updated screenshots

= 2.3.6 =
* Fixed: missing priority in template_include hook caused not activating mixed content fixer in some themes

= 2.3.5 =
* Fixed: javascript redirect insertion

= 2.3.4 =
* Tweak: load css stylesheet only on options page and before enabling ssl
* Tweak: mixed content fixer triggered by is_ssl(), which prevents fixing content on http.
* Start detection and configuration only for users with "manage_options" capability

= 2.3.3 =
* Fixed bug in force-deactivate script

= 2.3.2 =
* Changed SSL detection so test page is only needed when not currently on SSL.
* Some minor bug fixes.

= 2.3.1 =
* Removed "activate ssl" option when no ssl is detected.
* Optimized emptying of cache
* Fixed some bugs in deactivation and activation of multisite

= 2.3.0 =
* Gave more control over activation process by explicitly asking to enable SSL.
* Added a notice if .htaccess is not writable

= 2.2.20 =
Fixed a bug in SSL detection

= 2.2.19 =
Changed followlocation in curl to an alternative method, as this gives issues when safemode or open_basedir is enabled.
Added dismissable message when redirects cannot be inserted in the .htaccess

= 2.2.18 =
Fixed bug in logging of curl detection

= 2.2.17 =
Security fixes in ssl-test-page.php

= 2.2.16 =
Bugfix with of insecure content fixer.

= 2.2.13 =
Added a check if the mixed content fixer is functioning on the front end
Fixed a bug where multisite per_site_activation variable wasn't stored networkwide
Added clearing of wp_rocket cache thans to Greg for suggesting this
Added filter so you can remove the really simple ssl comment
Fixed a bug in the output buffer usage, which resolves several issues.
Added code so JetPack will run smoothly on SSL as well, thanks to Konstantin for suggesting this

= 2.2.12 =
* To prevent lockouts, it is no longer possible to activate plugin when wp-config.php is not writable. In case of loadbalancers, activating ssl without adding the necessary fix in the wp-config would cause a redirect loop which would lock you out of the admin.
* Moved redirect above the WordPress rewrite rules in the htaccess file.
* Added an option to disable the fallback javascript redirection to https.

= 2.2.11 =
Brand new content fixer, which fixes all links on in the source of your website.

= 2.2.10 =
* Roll back of mixed content fixer.

= 2.2.9 =
Improved the mixed content fixer. Faster and more effective.

= 2.2.8 =
Edited the wpconfig define check to prevent warnings when none are needed.

= 2.2.7 =
* Extended detection of homeurl and siteurl constants in wp-config.php with regex to allow  for spaces in code.
* Changed text domain to make this plugin language packs ready
* Added 404 detection to SSL detection function, so subdomains can get checked properly on subdomain multisite installs

= 2.2.6 =
Added slash in redirect rule
small bugfixes

= 2.2.3 =
documentation update

= 2.2.2 =
* Added multisite support for the missing https server variable issue
* Improved curl connection script
* Added French translation thanks to Cedric

= 2.2.1 =
* Small bug fixes

= 2.2.0 =
* Added per site activation for multisite, but excluded this option for subfolder installs.
* Added script to easily deactivate the plugin when you are locked out of the WordPress admin.
* Added support for a situation where no server variables are given which can indicate SSL, which can cause WordPress to generate errors and redirect loops.
* Removed warning on WooCommerce force SSL after checkout, as only unforce SSL seems to be causing problems
* Added Russian translation, thanks to xsascha
* Improved redirect rules in the .htaccess
* Added option te disable the plugin from editing the .htaccess in the settings
* Fixed a bug where multisite would not deactivate correctly
* Fixed a bug where insecure content scan would not scan custom post types

= 2.1.18 =
* Made WooCommerce warning dismissable, as it does not seem to cause issues
* Fixed a bug caused by WP native plugin_dir_url() returning relative path, resulting in no SSL messages

= 2.1.17 =
* Fixed a bug where example .htaccess rewrite rules weren't generated correctly
* Added WooCommerce to the plugin conflicts handler, as some settings conflict with this plugin, and are superfluous when you force your site to SSL anyway.
* Excluded transients from mixed content scan results

= 2.1.16 =
* Fixed a bug where script would fail because curl function was not installed.
* Added debug messages
* Improved FAQ, removed typos
* Replaced screenshots

= 2.1.15 =
* Improved user interface with tabs
* Changed function to test SSL test page from file_get_contents to curl, as this improves response time, which might prevent "no SSL messages"
* Extended the mixed content fixer to replace src="http:// links, as these should always be https on an SSL site.
* Added an error message in case of force rewrite titles in Yoast SEO plugin is used, as this prevents the plugin from fixing mixed content

= 2.1.14 =
* Added support for loadbalancer and is_ssl() returning false: in that case a wp-config fix is needed.
* Improved performance
* Added debugging option, so a trace log can be viewed
* Fixed a bug where the rlrsssl_replace_url_args filter was not applied correctly.

= 2.1.13 =
* Fixed an issue where in some configurations the replace url filter did not fire

= 2.1.12 =
* Added the force SSL option, in cases where SSL could not be detected for some reason.
* Added a test to check if the proposed .htaccess rules will work in the current environment.
* Readded HSTS to the htaccess rules, but now as an option. Adding this should be done only when you are sure you do not want to revert back to http.

= 2.1.11 =
* Improved instructions regarding uninstalling when locked out of back-end

= 2.1.10 =
* Removed HSTS headers, because it is difficult to roll back.

= 2.1.9 =
* Added the possibility to prevent htaccess from being edited, in case of redirect loop.
= 2.1.7 =
* Refined SSL detection
* Bugfix on deactivation of plugin

= 2.1.6 =
* Fixed an SSL detection issue which could lead to redirect loop

= 2.1.4 =
* Improved redirect rules for .htaccess

= 2.1.3 =
* Now plugin only changes .htaccess when one of three preprogrammed ssl types was recognized.
* Simplified filter use to add your own urls to replace, see f.a.q.
* Default javascript redirect when .htaccess redirect does not succeed

= 2.1.2 =
* Fixed bug where number of options with mixed content was not displayed correctly

= 2.1.1 =
* limited the number of files, posts and options that can be show at once in the mixed content scan.

= 2.1.0 =
* Added version control to the .htaccess rules, so the .htaccess gets updated as well.
* Added detection of loadbalancer and cdn so .htaccess rules can be adapted accordingly. Fixes some redirect loop issues.
* Added the possibility to disable the auto replace of insecure links
* Added a scan to scan the website for insecure links
* Added detection of in wp-config.php defined siteurl and homeurl, which could prevent from successful url change.
* Dropped the force ssl option (used when not ssl detected)
* Thanks to Peter Tak, [PTA security](http://www.pta-security.nl/) for mentioning the owasp security best practice https://www.owasp.org/index.php/HTTP_Strict_Transport_Security in .htaccess,

= 2.0.7 =
* Added 301 redirect to .htaccess for seo purposes

= 2.0.3 =
* Fixed some typos in readme
* added screenshots
* fixed a bug where on deactivation the https wasn't removed from siturl and homeurl

= 2.0.0 =
* Added SSL detection by opening a page in the plugin directory over https
* Added https redirection in .htaccess, when possible
* Added warnings and messages to improve user experience
* Added automatic change of siteurl and homeurl to https, to make backend ssl proof.
* Added caching flush support for WP fastest cache, Zen Cache and W3TC
* Fixed bug where siteurl was used as url to fix instead of homeurl
* Fixed issue where url was not replaced on front end, when used url in content is different from home url (e.g. http://www.domain.com as homeurl and http://domain.com in content)
* Added filter so you can add cdn urls to the replacement script
* Added googleapis.com/ajax cdn to standard replacement script, as it is often used without https.

= 1.0.3 =
* Improved installation instructions

== Upgrade notice ==
On settings page load, the .htaccess file is no rewritten. If you have made .htaccess customizations to the RSSSL block and have not blocked the plugin from editing it, do so before upgrading.
Always back up before any upgrade. Especially .htaccess, wp-config.php and the plugin folder. This way you can easily roll back.

== Screenshots ==
1. After activation, if SSL was detected, you can enable SSL.
2. View your configuration on the settings page.
3. Mixed content scan.

== Frequently asked questions ==
* Really Simple SSL maintains an extensive knowledge-base at https://www.really-simple-ssl.com.
