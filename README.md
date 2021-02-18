# Php7 + Apache + SSMTP

This image add [ssmtp](https://wiki.archlinux.org/index.php/SSMTP) service to official
[Docker Php7 Apache image](https://github.com/docker-library/php/blob/fd8e15250a0c7667b161c34a25f7916b01f72367/7.2/stretch/apache/Dockerfile).

With *ssmtp** you can use buildin [mail](http://php.net/manual/en/function.mail.php) Php function
to send mails via smtp server.

This image enable also [Apache Rewrite mod](http://httpd.apache.org/docs/current/mod/mod_rewrite.html), *RewriteEngine* can be used in [.htaccess](www/.htaccess).

```
version: '3'
services:
  apache:
    image: harobed/php-ssmtp:7-apache
    environment:
      - SSMTP_HOST=postfix
      - SSMTP_PORT=25
    ports:
      - 80
```