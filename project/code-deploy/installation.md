# Installation







First thing first, lets clone the repository

```bash
git clone https://github.com/rupadana/code-deploy
```

change your directory to project and install packages

```bash
composer install
```

Run this command to setup .env file or you can do it manually.

```bash
composer run-script post-root-package-install
```

Generate laravel app key using :

```bash
php artisan key:generate --ansi
```

Run this command to migrate & create <mark style="color:blue;">super admin</mark> user

```bash
php artisan shield:install
```

Log in to dashboard [http://127.0.0.1:8000<mark style="color:blue;">/app/login</mark>](http://127.0.0.1:8000/app/login) and create team!

