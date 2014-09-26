wp-ezdeveloper-ref-doc-security
===============================

A collection of knowledge as it relates to WordPress security.
===========================================================================================

## Pre-install

##### Add a Unique Database Prefix

Note that you should also change the default WordPress database table prefix. This is to secure your installation against hacks, such as the recent outbreak of the Pharma Hack. Visit random.org to generate a random prefix string which you'll need to set as the $table_prefix in wp-config.php. In addition, make sure to add an underscore at the end of the prefix.

- **Source: http://code.tutsplus.com/tutorials/20-steps-to-a-flexible-and-secure-wordpress-installation--wp-13236**
 

## Post-Install

##### .htaccess changes

- **Source: http://code.tutsplus.com/tutorials/20-steps-to-a-flexible-and-secure-wordpress-installation--wp-13236**


##### Protect wp-config.php  + Protect .htaccess

As mentioned earlier, the wp-config.php file contains all the confidential details of your site. So it's pretty important that you protect it at all costs. An easy way to protect this file is to simply place the following code in your .htaccess file on your server.

<Files wp-config.php>
   order allow,deny
   deny from all
</Files>


<Files .htaccess>
   order allow,deny
   deny from all
</Files>


- **Source: http://code.tutsplus.com/tutorials/11-quick-tips-securing-your-wordpress-site--wp-22446**


##### Disable file editing via the dashboard

In a default WordPress installation, you can navigate to Appearance > Editor and edit any of your theme files right in the dashboard. The trouble is, if a hacker managed to gain access to your admin panel, they could also edit your files that way, and execute whatever code they wanted to. So it’s a good idea to disable this method of file editing, by adding the following to your wp-config.php file:

define( ‘DISALLOW_FILE_EDIT’, true );

- **Source: http://www.woothemes.com/2013/09/improve-your-wordpress-security-with-these-10-tips**

Note: This can also be done via hooks, in the event you want to still allow some user to use editing.


##### Hide Your Plugins

Putting a blank index file into your /wp-content/plugins/ folder will hide all of your plugins. Some of you are probably thinking, "Who cares if someone can see my plugins?". Well, plugins can tell hackers how to hack your site, or at least if it is hackable.

- **Source: http://code.tutsplus.com/articles/10-steps-to-securing-your-wordpress-installation--wp-21579**


===========================================================================================

## Plugins


##### Clef

The easiest and most secure way to log in to WordPress: no passwords, no temporary codes, single sign-on/off.

- https://wordpress.org/plugins/wpclef/
- https://getclef.com/


##### Acunetix WP Security

Scans your WordPress installation for security vulnerabilities.

- https://wordpress.org/plugins/wp-security-scan/
 

##### Sucuri Security

Auditing, Malware Scanner and Hardening

= https://wordpress.org/plugins/sucuri-scanner/


##### iThemes Better WP Security

The easiest, most effective way to secure WordPress in seconds.

- https://wordpress.org/plugins/better-wp-security/


##### Wordfence Security

Wordfence Security is a free enterprise class security and performance plugin that makes your site up to 50 times faster and more secure.

- https://wordpress.org/plugins/wordfence/


===========================================================================================

## Sources & Resources

#### WordPress Web Application Firewall – BBQ:Block Bad Queries
- http://www.wpwhitesecurity.com/wordpress-plugins/wordpress-web-application-firewall-bbq-block-bad-queries/

#### Sept 2014 - The WordPress Developer’s Guide to Security: Security & Backup Plugins
 - https://managewp.com/wordpress-security-backup-plugins


#### Sept 2014 - Understanding the WordPress Security Plugin Ecosystem
- http://blog.sucuri.net/2014/09/understanding-the-wordpress-security-plugin-ecosystem.html


#### Sept 2014 - Bad Bot .htaccess, List (Updates Log)
 - http://pastebin.com/r1TvzT6p


#### Sept 2014 - Asset Access Restriction Methods – Block Unwanted Visitors
 - http://www.sitepoint.com/asset-access-restriction-methods-block-unwanted-visitors/
 

#### Sept 2014 - Why You Should Change the WordPress Administrator User ID
- http://www.wpwhitesecurity.com/wordpress-security/change-wordpress-administrator-id/


#### Aug 2014 - My WordPress Website Was Hacked
- http://blog.sucuri.net/2014/08/my-wordpress-website-was-hacked.html


#### Aug 2014 - Is My Website Ready for Some Serious Hacks?
- http://www.1stwebdesigner.com/design/serious-hacks-website/
