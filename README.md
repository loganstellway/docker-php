# About this Repo
This is the GIT repository for a `PHP` Docker image. 

## Tags
  - `7.0-fpm-alpine-magento2`
  - `7.0-fpm-alpine-magento2-full`
  - `7.1-fpm-alpine-magento2`
  - `7.1-fpm-alpine-magento2-full`

## Initializing Scripts
When a container is started for the first time, the entrypoint script will execute `.sh` mounted to the `/docker-entrypoint-initphp.d` directory. 

>docker run --name composer -v /my/own/scripts/:/docker-entrypoint-initphp.d/ -d lstellway/php:7.0-magento2-full

## Magento 2 Dependencies
Images have been created according to the [Magento 2 technology stack requirements](http://devdocs.magento.com/guides/v2.1/install-gde/system-requirements-tech.html#php), utilizing the following PHP packages:
  - [gd](http://php.net/manual/en/book.image.php)
  - [mcrypt](http://php.net/manual/en/book.mcrypt.php)
  - [xsl](http://php.net/manual/en/book.xsl.php)
  - [intl](http://php.net/manual/en/book.intl.php)
  - [pdo_mysql](http://php.net/manual/en/ref.pdo-mysql.php)
  - [zip](http://php.net/manual/en/book.zip.php)
  - [soap](http://php.net/manual/en/book.soap.php)
  - [opcache](http://php.net/manual/en/book.opcache.php)

## Extended Dependencies
Images have alternate version tags suffixed with `-full` that include further dependencies:
  - [GIT](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
  - [Composer](https://getcomposer.org/)

## Issues / Suggestions
Please feel free to fork, contribute and report issues!
