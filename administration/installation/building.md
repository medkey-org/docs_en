---
description: >-
  How to get custom manual distribution build of  Medkey Hospital Information
  System
---

# Building from source code

## **Prerequisites**

* Having linux OS or Linux subsystem for Windows
* Superuser access \(sudo/root\) to execute all listed below commands/programs
* Installed Git SCM, accessible using environment alias `git`
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

## 2. Cloning Hospital Information System Medkey source code

Our main repository hosted on GitHub. To get latest version of source code, for example, to your home directory \(`cd ~`\), and then execute command:

{% tabs %}
{% tab title="Via SSH" %}
```text
git clone git@github.com:medkey-org/medkey.git
```
{% endtab %}

{% tab title="Via HTTPS" %}
```text
git clone https://github.com/medkey-org/medkey.git
```
{% endtab %}
{% endtabs %}

After cloning your source code will be located at `~/medkey` directory. You can specify any other suitable for you directory. Directory with Medkey repository files are named base application directory.

## 3. Installing application dependencies using Composer

Go to base application directory. There execute command:

```text
composer install
```

It will take some minutes, wait a bit.

## 4. Installing frontend dependencies

Go to directory frontend inside base application directory \(for example, `~/medkey/frontend`\). Then execute command:

```text
npm install
```

## 5. Building frontend bundles

Go to directory frontend inside base application directory \(for example, `~/medkey/frontend`\). Then execute command:

```text
npm run build-dev
```

## 6. Packing built application

Go to parent directory of base application directory \(fo `~/medkey` it will be `~`\). Execute command:

```text
tar -zcvf medkey.tar.gz medkey
```

After completion you will have built distribution of you application, which can be distributed on any server, and can be installed using [installation guides](./).

