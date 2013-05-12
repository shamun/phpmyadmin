Red hat linux:

here are a few steps
1. Download the latest version of phpMyAdmin from www.phpmyadmin.net
or
https://github.com/shamun/phpmyadmin/raw/master/phpMyAdmin-4.0.0-all-languages.zip

2. unpack the package
cd /var/tmp
unzip phpMyAdmin-4.0.0-all-languages.zip

3. Move it to the appropriate place.
mv phpMyAdmin-4.0.0-all-languages /usr/share/

4. Configure phpMyAdmin
cd /usr/share/phpMyAdmin-4.0.0-all-languages
cp config.sample.inc.php config.inc.php
vim config.inc.php

5. Locate each of the following lines and be sure each has the following settings.
$cfg['Servers'][$i]['auth_type'] = 'http'; // config - to auto login, http - to prompt for login name / pass
$cfg['Servers'][$i]['user'] = 'root'; // MySQL? user
$cfg['Servers'][$i]['password'] = 'pass'; // MySQL? password (only nee$

6. Save the file.

7. Create the apache config file for phpmyadmin and restart apache.
echo "alias /phpmyadmin /usr/share/phpMyAdmin-4.0.0-all-languages" > /etc/httpd/conf.d/phpMyAdmin.conf
service httpd restart


now visit http://site/phpmyadmin 
it will ask user/pass


