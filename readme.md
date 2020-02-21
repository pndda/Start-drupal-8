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
!! will not work at first !!

go to folder > web > sites > default > settings.php

add > in $database 

```
$database(

 'unix_socket' => '/Applications/MAMP/tmp/mysql/mysql.sock',
)

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
