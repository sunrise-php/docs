# sunrise/awesome-skeleton :id=top

An awesome skeleton for modern PHP development.

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/awesome-skeleton/php?style=social&logo=php&label=PHP)
![Downloads](https://img.shields.io/packagist/dt/sunrise/awesome-skeleton?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/awesome-skeleton?style=social)

> Awesome Skeleton is based on the [PHP-DI](https://php-di.org/) container.
> Study it to better understand your project.

## Key Features

- Immutable architecture
- Direct injection of DTO objects into controllers
- Sending View objects directly from controllers
- Self-documenting API
- Localization
- Error handling
- High flexibility

## Installation

```bash
composer create-project sunrise/awesome-skeleton
```

## Running

Use the following command to run your project on the built-in web server, accessible at `localhost:8000`:

> The [built-in web server](https://www.php.net/manual/en/features.commandline.webserver.php) must be used for demonstration purposes only.

> Data can be requested in a different language and format using the `Accept-Language` and `Accept` headers.

```bash
php -S localhost:8000 public/index.php
```

![Screenshot](media/welcome-html-screenshot.png)

## CLI

```bash
php bin/app
```

![Screenshot](media/cli-screenshot.png)

## Production

Make sure the cache is configured in:

```text
config/definitions/prod/cache.php
```

Make sure the value of the environment variable `APP_ENV` is set to `prod`:

```ini
APP_ENV=prod
```

Make sure the following command is run after deployment:

```bash
php bin/app router:clear-descriptors-cache
```

## What's Next :id=what-is-next

- Create your first [API operation](/docs/cookbook/user-sign-in-operation.md).

## Tests

```bash
composer test
```
