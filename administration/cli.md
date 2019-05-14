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
For example, Medkey files located in `/var/www/medkey`. Execute command:

```text
cd /var/www/medkey
```
{% endtab %}

{% tab title="Windows \(cmd/Powershell\)" %}
```text
cd /var/www/medkey
```
{% endtab %}
{% endtabs %}



## Command reference

### Installing migrations

Medkey use migration mechanism to deploy and upgrade database structure.

### 

