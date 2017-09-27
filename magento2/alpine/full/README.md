# Docker PHP For Magento 2
Docker PHP image including PHP dependencies for Magento 2

## Added PHP Packages
  - gd
  - mcrypt
  - xsl
  - intl
  - pdo_mysql
  - zip
  - soap
  - opcache

## Other Includes
  - GIT
  - Composer

## Initializing a Fresh Instance
When a container is started for the first time, the entrypoint script will execute `.sh` files in the `/docker-entrypoint-initphp.d` directory. 

>docker run --name composer -v /my/own/scripts/:/docker-entrypoint-initphp.d/ -d lstellway/php:magento2-alpine-full
