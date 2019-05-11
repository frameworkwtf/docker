# WTF Framework dockerized [![Docker Pulls](https://img.shields.io/docker/pulls/frameworkwtf/docker.svg?style=for-the-badge)](https://hub.docker.com/r/frameworkwtf/docker/)

## Table of Contents


<!-- vim-markdown-toc GFM -->

+ [How to use](#how-to-use)
+ [Integrated tools](#integrated-tools)

<!-- vim-markdown-toc -->

# How to use

Create `Dockerfile` in your poject root with following contents:

```Dockerfile
FROM frameworkwtf/docker

COPY . /var/www
```

Build and run it, that's all.

# Integrated tools

1. **Swagger builder [swagger-php](https://github.com/zircote/swagger-php)** - If your project has swagger-php installed, it will be runned automatically on container start
2. **Phinx migrations and seed [phinx](http://phinx.org)** - If your project has phinx installed, migrations will be runned on container start. **IF** your **APP_ENV** env var **IS NOT** "prod", seeds will be runned after migrations
3. Console - If your project contains `app/public/console.php` file, you can run it simple with `console` from any part of the system. Very helpful when you want to add some cron scrits or run it via `docker exec`. No matter which console library you use
4. cron - [manual](https://wiki.alpinelinux.org/wiki/Alpine_Linux:FAQ#My_cron_jobs_don.27t_run.3F)
5. nginx
6. php-fpm
