Acquia Memcache settings
====

This is a Composer package providing a recommended set of Memcache settings for use with Acquia Cloud and Acquia Cloud Site Factory.

These settings are continuously updated based on the [publicly available documentation](https://docs.acquia.com/acquia-cloud/performance/memcached/enable/).

## Installation and usage

To use these settings, you must already have configured a [Composer-based Drupal project](https://github.com/drupal-composer/drupal-project/blob/8.x/composer.json). Especially, ensure that your root composer.json includes the Drupal packagist repository and Drupal-specific installer paths. Then require this package via Composer:

`composer require acquia/memcache-settings`

Finally, you must include the provided `memcache.settings.php` in your own settings.php file (for Acquia Cloud) or post-settings-php hook (for Acquia Cloud Site Factory):
```
$repo_root = dirname(DRUPAL_ROOT);
$memcacheSettingsFile = $repo_root . '/vendor/acquia/memcache-settings/memcache.settings.php';
if (file_exists($memcacheSettingsFile)) {
  require $memcacheSettingsFile;
}
```

Note that if you use [Acquia BLT](https://github.com/acquia/blt), this step is unnecessary as BLT will automatically include this file.

# License

Copyright (C) 2020 Acquia, Inc.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License version 2 as published by the Free Software Foundation.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.
