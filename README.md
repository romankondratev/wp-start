# Wordpress
Данное руководство отображает основые шаги по развертыванию локального проекта на WordPress.

## Установка
Необходимо скачать и распоковать последнюю версию WordPress на тестовый сервер.

### Zip:
https://ru.wordpress.org/latest-ru_RU.zip

### Linux:
```
wget https://ru.wordpress.org/latest-ru_RU.zip
unzip latest-ru_RU.zip
```

### Mac OSX:
```
curl -O https://ru.wordpress.org/latest-ru_RU.zip
unzip latest-ru_RU.zip
```


Меняем права на проект:
```Shell
sudo chown -R www:staff .
sudo chmod -R 774 .
```

## Настройка
### wp-config.php
```PHP
/**
 * Ограничиваем количество редакций.
 */
define( 'WP_POST_REVISIONS', 10 );


/**
 * Обновление без FTP.
 */
define( 'FS_METHOD', 'direct' );
```

## Плагины
### wp-content/plugins
Устанавливаем необходимые плагины.


#### Advanced Custom Fields PRO (платный)
https://wordpress.org/plugins/advanced-custom-fields/

PRO-версию необходимо скачать с официального сайта:

http://www.advancedcustomfields.com/my-account/


#### Cyr to Lat enhanced
https://wordpress.org/plugins/cyr3lat/

Для загрузки изображений "@2x" вносим изменения в файл `wp-content/plugins/cyr3lat/cyr-to-lat.php`
```
$title = preg_replace("/[^A-Za-z0-9'_\-\.]/", '-', $title);
``` 
на
```
$title = preg_replace("/[^A-Za-z0-9'_\-\.@]/", '-', $title);
```


#### Custom Upload Dir
https://wordpress.org/plugins/custom-upload-dir/

В настройках `Build a path template:` указываем `/%post_type%/%post_id%/%file_type%`


#### Prime Strategy Bread Crumb
https://wordpress.org/plugins/prime-strategy-bread-crumb/


#### Scripts-To-Footer
https://wordpress.org/plugins/scripts-to-footerphp/


#### Simple Page Ordering
https://wordpress.org/plugins/simple-page-ordering/