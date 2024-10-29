=== Backup Database Phpmyadmin ===
Tags: db, mysql, database, backup, cron
Requires at least: 3.6.0
Tested up to: 5.4
Stable tag: 1.0.0
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Backup Database to Phpmyadmin. 

== Description ==
Create backup of database tables easily or set cron to regularly take backups daily, monthly, once an year, etc.


== Installation ==
* Upload the Backup Database Phpmyadmin plugin to the `/wp-content/plugins/` directory
* Activate the plugin through the 'Plugins' menu in WordPress


== Frequently Asked Questions ==

= How to open Backup Database Phpmyadmin in dashboard? =
* Navigate to Tools >> Backup

= How to restore my database from a backup? =
* You can restore it in phpmyadmin which is available in cpanel. 

= My backup is stopping or it hangs without completing. =
* If you edit the text of backup-database.php, you’ll see around line 50 the following:

`/**
* Set MOD_EVASIVE_OVERRIDE to true
* and increase MOD_EVASIVE_DELAY
* if the backup stops prematurely.
*/
// define('MOD_EVASIVE_OVERRIDE', false);
define('MOD_EVASIVE_DELAY', '500');`

Do what it says: un-comment MOD_EVASIVE_OVERRIDE and set it to true like so:

`define('MOD_EVASIVE_OVERRIDE', true);`

That will slow down the plugin, and you can slow it even further by increasing the MOD_EVASIVE_DELAY number from 500.

Better yet, put the lines that define the `MOD_EVASIVE_OVERRIDE` and `MOD_EVASIVE_DELAY` constants in your wp-config.php file, so your settings don't get erased when you upgrade the plugin.


== Changelog ==

= 1.0.0 =
* Initial release

