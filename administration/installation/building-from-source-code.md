# Building from source code

## **Prerequisites**

* Having linux OS or Linux subsystem for Windows
* Superuser access \(sudo/root\) to execute all listed below commands/programs
* Installed PHP 7.3 with modules or, at least PHP 7.2  with modules, accessible using environment alias `php`
* Installed Composer, accessible using environent alias `composer`
* Installed NodeJS 11.x or higher version, accessible using enrivonment alias `node`
* Installed NPM 6.x or higher version, accessible using environment alias `npm`

## **1. Checking environment**

In you are sure in your environment compatibility, you can miss this step. In other cases execute next commands and compare your output with required:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Command</th>
      <th style="text-align:left">Required output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>php -v</code>
      </td>
      <td style="text-align:left">Must output at minimum version 7.2.x</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>php -m</code>
      </td>
      <td style="text-align:left">
        <p>Must output the next list of modules:</p>
        <p><code>code bcmath calendar Core ctype curl date dom exif fileinfo filter ftp gd gettext hash iconv imap intl json libxml mailparse mbstring openssl pcntl pcre PDO pdo_pgsql pgsql Phar posix readline Reflection session shmop SimpleXML soap sockets sodium SPL standard sysvmsg sysvsem sysvshm tidy tokenizer wddx xml xmlreader xmlwriter xsl Zend OPcache zip zlib mysqli mysqlnd pdo_mysql</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>node -v</code>
      </td>
      <td style="text-align:left">Must output at minimum version 11.x</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>npm -v</code>
      </td>
      <td style="text-align:left">Must output at minimum version 6.x</td>
    </tr>
  </tbody>
</table>If everything is correct, continue to the next step.



