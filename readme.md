# How to start a drupal project 2020 

## Installation

Use [composer](https://getcomposer.org/)  to install drupal locally. 

```
composer create-project drupal/recommended-project my_site_name_dir
```

## Install drush 
For import- export database, cache refresh 

```
composer require drush/drush 
```
**!! will not work at first !!**

go to folder > web > sites > default > settings.php
1. add > in $database 
2. uncomment

```
1. 
$database(

 'unix_socket' => '/Applications/MAMP/tmp/mysql/mysql.sock',
)
2. 
# if (file_exists($app_root . '/' . $site_path . '/settings.local.php')) {
# include $app_root . '/' . $site_path . '/settings.local.php';
# }
```

go to development.services.yml 
add 
```
parameters:
  http.response.debug_cacheability_headers: true
  twig.config:
    debug: true
    auto_reload: true
    cache: false
services:
  cache.backend.null:
    class: Drupal\Core\Cache\NullBackendFactory
```
#### Usage

```
Cache refresh
   drush cr
Export config files
   drush cex
Import config files
   dursh cim -y 
   drush updb -y
```
