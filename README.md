1. create user field

site admin>users>User profile fields

shortname=authcookies
shortname=validationkey
>> as text
>> restrict to the spelling --used as it is --hard coded in code --week point 


3. in lib.php, after_require_login function to triger after login

7. add activity>>Restrict access>>user profile>>auth. from  cookies is >>OK
after_require_login

how to test

1. local/mancookies/manage.php
will list all users then click create cookies per each user

so when i click create cookies will collect validationkey from db and create cookies
2. after login will fire function that compare validationkey from db and cookies if ok set authcookies to ok

 if not set to notok
3. make an activity per quiz under course, restrict access by user profile auth. cookies to equal to ok

>>>remove_dir($CFG->dataroot.'/cache', true);
root@home:/var/www/html/moodle# php admin/cli/purge_caches.php
root@home:/var/www/html/moodle# 

https://stackoverflow.com/questions/29901227/does-moodle-cache-user-profile-field-for-activity-restriction

Great - thanks -
I found some references in the 
icode that allows the user to
manage preferences, based on my 
comment. The one that I think has
done the trick is profile_load_
custom_fields($USER); – 
Martin Greenaway
CommentedApr 28, 2015 at 13:40
*******
add if stat. to test if user is loggedin or not
to let guest user visit the site
*********
Adding limit create cookies to admin only
should install or upgrade because 

2. Get Moodle to load the updated capabilities
The capabilities you defined are only read (and copied into the Moodle database) when your module is installed or upgraded. So every time you edit the db/access.php file you must

Increase your module's version number by editing the file mod/<<NEWMODULE>>/version.php.
Go to the the Administration ► Notifications page, and click through the steps to let Moodle upgrade itself. You should see the name of your module in one of the steps.


ref. https://docs.moodle.org/dev/NEWMODULE_Adding_capabilities
