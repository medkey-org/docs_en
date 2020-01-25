# Installing on Debian/Ubuntu

## Installing on Debian 9 Stretch

### Checkup before you start

* Installed Debian 9 Stretch;
* You have root \(sudo\);
* You have installed Apache2;
* You have installed PostgreSQL;
* You have installed PHP 7.2;
* You've created empty database on PostgreSQL.

### Installation steps

1. Create VirtualHost file inside `/etc/apache2/sites-available`:
   1. `touch /etc/apache2/sites-available/medkey`
2. Copy VirtualHost config sample at the bottom of current page.
3. Activate VHost and restart server:
   1. `a2ensite medkey`
   2. `service apache2 reload`
4. Download Medkey .tar.gz:
   1. `cd /tmp` // Goto temporary directory
   2. `wget --output-document medkey.tar.gz https://bitbucket.org/medkey/builds/downloads/medkey_VERSION.tar.gz` // Replace VERSION word by actual version from repository.
5. Unpack .tar.gz inside /var/www using tar -zxvf:
   1. `cp medkey.tar.gz -t /var/www` // Copy file inside target directory
   2. `cd /var/www` // Go to target
   3. `tar -zxvf medkey.tar.gz` // Untar
6. Copy file env.prod.php to env.php: `cp env.prod.php env.php`
7. Inside\`env.php\` using your text editor setup database connection parameters:
   1. `define('APP_DB_HOST', '127.0.0.1');` // Database server IP address
   2. `define('APP_DB_PORT', '5432');` // Database server port/cluster port
   3. `define('APP_DB_NAME', 'medkey');` // Database name
   4. `define('APP_DB_USERNAME', 'postgres');` // Database user
   5. `define('APP_DB_PASSWORD', '12345');` // Database user password
8. Execute migrate command \(creates database tables structure\):
   1. `php medkey migrate`
9. Execute seed command \(fills your database with initial data\):
   1. `php medkey seed package install`

### Installation checkup

Login using \`admin:admin\` \(логин:пароль\) with your browser.

### Configuration samples

#### Config for VirtualHost at Apache2

```text
<VirtualHost *:80>
    ServerName medkey.local

    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/medkey/web

    <Directory /var/www/medkey/web>
        RewriteEngine on
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteRule . index.php

        Options Indexes FollowSymLinks MultiViews
        AllowOverride None
        Order allow,deny
        allow from all
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/medkey.error.log
    CustomLog ${APACHE_LOG_DIR}/medkey.access.log combined
</VirtualHost>
```

