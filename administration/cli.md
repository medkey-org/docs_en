---
description: Medkey command line interface reference
---

# Command-line interface

If you installing HIS Medkey on your own server or VPS/VDS, you will need to use command line commands.

## Prerequisites

* Installed PHP command line application \(will be installed by default using typical Linux packages and using PHP installer for Windows\), available using `php` command from shell
* Superuser access \(root\) for Linux systems
* Deployed Medkey application files

## Using CLI entry point

To use CLI entry point go to Medkey application directory \(where Medkey application installed\)**.**

{% tabs %}
{% tab title="Linux \(bash\)" %}
For example, Medkey files located in `/var/www/medkey`. To go to Medkey deployment directory execute command:

```text
cd /var/www/medkey
```
{% endtab %}

{% tab title="Windows \(cmd/Powershell\)" %}
For example, Medkey files located in `C:\htdocs\medkey`. Execute command:

```text
cd C:\htdocs\medkey
```
{% endtab %}
{% endtabs %}

To execute CLI commands use signature below:

{% tabs %}
{% tab title="Linux \(bash\)" %}
```text
php bin <command> <arguments>
```
{% endtab %}

{% tab title="Windows \(cmd/Powershell\)" %}
```text
bin.bat <command> <arguments>
```
{% endtab %}
{% endtabs %}

## Command reference

### `migrate` command

Medkey use migration mechanism to deploy and upgrade database structure.

### `seed` command

Medkey use seed mechanism to fill database with predefined data packages.



