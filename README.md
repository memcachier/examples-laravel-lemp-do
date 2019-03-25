# MemCachier and Laravel example (DigitalOcean using one-click LEMP stack)

This is an example Laravel 5.8 task list app that uses a
[MemCachier](https://www.memcachier.com) cache. It is configured for
deployment on [DigitalOcean](https://www.digitalocean.com/) using
DigitalOcean's [one-click LEMP
stack](https://marketplace.digitalocean.com/apps/lemp).

Detailed instructions for developing this app are available
[here](https://blog.memcachier.com/2019/xx/xx/laravel-memcache-do-lemp).

## Running Locally

Run the following commands to get started running this app locally:

```sh
$ git clone https://github.com/memcachier/examples-laravel-lemp-do.git
$ cd examples-laravel-lemp-do
$ composer install
$ touch database/database.sqlite
$ php artisan migrate --force
$ echo "APP_KEY=`php artisan key:generate --show`" > .env
$ memcached &  # run a local memcached server instance
$ php artisan serve
```

Then visit `http://localhost:8000` to play with the app.

Note: instead of running a local `memcached` server you can also create a
[MemCachier](https://www.memcachier.com/) cache and add the `MEMCACHIER_*`
environment variables to `.env`.
