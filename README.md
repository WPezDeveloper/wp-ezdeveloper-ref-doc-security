# - - DRAFT - - 

wp-ezdeveloper-ref-doc-security
===============================

A collection of knowledge as it relates to WordPress security.

---

**"What this WPezDevelope Ref Doc stuff all about?"**

https://github.com/WPezDeveloper/wp-ezdeveloper-getting-started/blob/master/README.md

---



## Pre-install

#### Add a Unique Database Prefix

Note that you should also change the default WordPress database table prefix. This is to secure your installation against hacks, such as the recent outbreak of the Pharma Hack. Visit random.org to generate a random prefix string which you'll need to set as the $table_prefix in wp-config.php. In addition, make sure to add an underscore at the end of the prefix.

- **Source: http://code.tutsplus.com/tutorials/20-steps-to-a-flexible-and-secure-wordpress-installation--wp-13236**
 

## Post-Install


#### Move the wp-config.php

- **Source: http://premium.wpmudev.org/blog/daily-tip-improve-wordpress-security-by-moving-the-wp-config-php-file/**


#### Move the wp-content directory

In case you are wondering, you can change the name of wp-content to whatever you want. Doing so is especially useful if you have several local development servers running on your computer. If you do it will make searching for a particular site’s content directory much easier. In fact you can use the same method to rename wp-content without moving it.

Do keep in mind that moving or renaming wp-content may break certain poorly written plugins or themes that have hardcoded the plugin or theme directories instead of doing it the right way. Don’t let this stop you moving or renaming wp-content as you probably shouldn’t trust any plugin or theme that doesn’t define their directory location properly using constants.

- **Source: http://premium.wpmudev.org/blog/10-wp-config-tweaks-to-improve-your-wordpress-site/**


#### Move the plugins directory

So far we have assumed your plugin directory will be staying inside the content directory, but it doesn’t have to.

- **Source: http://premium.wpmudev.org/blog/10-wp-config-tweaks-to-improve-your-wordpress-site/**


#### Relocate the mu-plugins Directory

Must use plugins, aka “mu-plugins,” are plugins that run automatically on your site and cannot be disabled.
By default, WordPress will look for a directory called “mu-plugins” in the content directory to load mu-plugins from.

- **Source: http://premium.wpmudev.org/blog/10-wp-config-tweaks-to-improve-your-wordpress-site/**


#### Password Protect Your WordPress Admin (wp-admin) Directory

Step by step guide on how to password protect your WordPress admin (wp-admin) directory via .htaccess.

- **Source: http://www.wpbeginner.com/wp-tutorials/how-to-password-protect-your-wordpress-admin-wp-admin-directory/**
 
```

IMPORTANT http://codex.wordpress.org/Moving_WordPress#Moving_Directories_On_Your_Existing_Server

```

#### .htaccess changes

- **Source: http://code.tutsplus.com/tutorials/20-steps-to-a-flexible-and-secure-wordpress-installation--wp-13236**


#### Protect wp-config.php  + Protect .htaccess

As mentioned earlier, the wp-config.php file contains all the confidential details of your site. So it's pretty important that you protect it at all costs. An easy way to protect this file is to simply place the following code in your .htaccess file on your server.

```
<Files wp-config.php>
   order allow,deny
   deny from all
</Files>


<Files .htaccess>
   order allow,deny
   deny from all
</Files>
```

- **Source: http://code.tutsplus.com/tutorials/11-quick-tips-securing-your-wordpress-site--wp-22446**



#### Add Bad Bot list to .htaccess

- **Source: http://pastebin.com/r1TvzT6p**


#### Disable file editing via the dashboard

In a default WordPress installation, you can navigate to Appearance > Editor and edit any of your theme files right in the dashboard. The trouble is, if a hacker managed to gain access to your admin panel, they could also edit your files that way, and execute whatever code they wanted to. So it’s a good idea to disable this method of file editing, by adding the following to your wp-config.php file:

```
define( ‘DISALLOW_FILE_EDIT’, true );
```

- **Source: http://www.woothemes.com/2013/09/improve-your-wordpress-security-with-these-10-tips**

Note: This can also be done via hooks, in the event you want to still allow some user to use editing.


#### Hide Your Plugins

Putting a blank index file into your /wp-content/plugins/ folder will hide all of your plugins. Some of you are probably thinking, "Who cares if someone can see my plugins?". Well, plugins can tell hackers how to hack your site, or at least if it is hackable.

- **Source: http://code.tutsplus.com/articles/10-steps-to-securing-your-wordpress-installation--wp-21579**


#### Hide Login Error Messages

Error login messages may expose and give hackers an idea if they’ve gotten username correct/incorrect, vice versa. It is wise to hide it from unauthorized login.

To hide login error messages, simply put the following code in functions.php

```
// Security update hide error messages for failed login
function login_error_msg () {
  // Custom login error message
  $login_err_msg = "Invalid User Name or Password";
  return $login_err_msg;
}

add_filter('login_errors','login_error_msg');
```

- **Source: http://www.hongkiat.com/blog/hardening-wordpress-security/**

Note: It's best to have your own standard customizations plugin (and not always use the theme's functions.php) so you don't forget about things like this if / when you switch themes. Ideally, you'd make this plugin a must use plugin so there's no chance of it being deactivated.


#### Change the WordPress Administrator User ID

The WordPress administrator account is most probably the most targeted account on a WordPress blog or site. Therefore it is recommended to properly secure the WordPress administrator account.

One of the recommended security tweaks is to change the default ID assigned to the WordPress administrator user account. This WordPress security article explains why you should change the default WordPress administrator account ID and how to change it.

- **Source: http://www.wpwhitesecurity.com/wordpress-security/change-wordpress-administrator-id/**


#### Development: Sanitize, Escape and Validate

Sanitizing, Escaping and Validating Data in WordPress
- http://www.sitepoint.com/sanitizing-escaping-validating-data-in-wordpress/

WordPress.org Codex: Data Validation
- https://codex.wordpress.org/Data_Validation


===========================================================================================

## Plugins


#### WP Password Policy Manager

Improve the security of your WordPress blogs and websites by configuring strong WordPress policies to ensure all WordPress users use strong passwords.

- https://wordpress.org/plugins/wp-password-policy-manager/


#### Clef

Two-factor authentication - The easiest and most secure way to log in to WordPress: no passwords, no temporary codes, single sign-on/off.

- https://wordpress.org/plugins/wpclef/
- https://getclef.com/
- http://wptavern.com/password-free-login-with-clef-hits-all-the-high-notes
 

#### Google Authenticator

Two-factor authentication using the Google Authenticator app for Android/iPhone/Blackberry.

- https://wordpress.org/plugins/google-authenticator/
- http://www.wpwhitesecurity.com/wordpress-security/add-google-authenticator-wordpress/


#### WP Security Audit Log

Similar to the Windows Event Log or Syslog on Unix / Linux systems, WP Security Audit Log is a WordPress security monitoring plugin that logs all type of activity happening on your WordPress blog or website or WordPress Multisite network installation.

https://wordpress.org/plugins/wp-security-audit-log/


#### Acunetix WP Security

Scans your WordPress installation for security vulnerabilities.

- https://wordpress.org/plugins/wp-security-scan/
 

#### Sucuri Security

Auditing, Malware Scanner and Hardening

= https://wordpress.org/plugins/sucuri-scanner/


#### iThemes Better WP Security

The easiest, most effective way to secure WordPress in seconds.

- https://wordpress.org/plugins/better-wp-security/


#### Wordfence Security

Wordfence Security is a free enterprise class security and performance plugin that makes your site up to 50 times faster and more secure.

- https://wordpress.org/plugins/wordfence/
 

===========================================================================================

## Other

##### July 2015 - 10 Reasons To Use HTTPS
 - https://medium.com/so-now-you-know/10-reasons-to-go-https-a2cba5734bb6


===========================================================================================

## Sources & Resources

#### WordPress Web Application Firewall – BBQ:Block Bad Queries
- http://www.wpwhitesecurity.com/wordpress-plugins/wordpress-web-application-firewall-bbq-block-bad-queries/


#### Sept 2014 - The WordPress Developer’s Guide to Security: Security & Backup Plugins
 - https://managewp.com/wordpress-security-backup-plugins


#### Sept 2014 - Understanding the WordPress Security Plugin Ecosystem
- http://blog.sucuri.net/2014/09/understanding-the-wordpress-security-plugin-ecosystem.html


#### Sept 2014 - Asset Access Restriction Methods – Block Unwanted Visitors
 - http://www.sitepoint.com/asset-access-restriction-methods-block-unwanted-visitors/
 
#### Aug 2014 - My WordPress Website Was Hacked
- http://blog.sucuri.net/2014/08/my-wordpress-website-was-hacked.html


#### Aug 2014 - Is My Website Ready for Some Serious Hacks?
- http://www.1stwebdesigner.com/design/serious-hacks-website/
 

===========================================================================================

## TODOs

##### May 2017 - How To Run A WordPress Security Audit
 - https://ithemes.com/2017/05/17/how-to-run-a-wordpress-security-audit/

##### July 2016 - WordPress Security: The Ultimate 32-Step Checklist
 - https://premium.wpmudev.org/blog/ultimate-wordpress-security-checklist/


##### May 2016 - How to Tweak wp-config.php to Protect Your WordPress Site
 - https://premium.wpmudev.org/blog/tweaking-wp-config/

##### April 2016 - Everything You Need To Know About Security For WordPress
 - http://torquemag.io/2016/04/everything-need-know-security-wordpress/

10 Tips to Secure WordPress
http://www.sitepoint.com/tips-to-secure-wordpress

#### May 2015 - Securing WordPress Against Hackers and DDoS Attacks
- http://www.sitepoint.com/securing-wordpress-hackers-ddos-attacks
 
- http://premium.wpmudev.org/blog/set-up-wordpress-like-a-pro/

- http://www.elegantthemes.com/blog/tips-tricks/wordpress-wp-config-php

- http://www.wpwhitesecurity.com/wordpress-security/wordpress-security-plugins/

- http://www.wpwhitesecurity.com/definite-guide-htaccess-wordpress/
