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


##### Hide Your Plugins

Putting a blank index file into your /wp-content/plugins/ folder will hide all of your plugins. Some of you are probably thinking, "Who cares if someone can see my plugins?". Well, plugins can tell hackers how to hack your site, or at least if it is hackable.

- **Source: http://code.tutsplus.com/articles/10-steps-to-securing-your-wordpress-installation--wp-21579**


===========================================================================================

## Plugins

##### iThemes' Better WP Security

- https://wordpress.org/plugins/better-wp-security/


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
