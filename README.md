Addimg limit create cookies to admin only
should install or upgrade because 

2. Get Moodle to load the updated capabilities
The capabilities you defined are only read (and copied into the Moodle database) when your module is installed or upgraded. So every time you edit the db/access.php file you must

Increase your module's version number by editing the file mod/<<NEWMODULE>>/version.php.
Go to the the Administration ► Notifications page, and click through the steps to let Moodle upgrade itself. You should see the name of your module in one of the steps.


ref. https://docs.moodle.org/dev/NEWMODULE_Adding_capabilities
