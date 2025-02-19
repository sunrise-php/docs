# Awesome Skeleton

Awesome Skeleton for modern PHP 8.1+ development.

![Downloads](https://img.shields.io/packagist/dt/sunrise/awesome-skeleton?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/awesome-skeleton?style=social)

## System Requirements

PHP 8.1+

## Installation

```bash
composer create-project sunrise/awesome-skeleton awesome-app/
```

> Don't forget to navigate to your new project’s directory.

```bash
cd awesome-app/
```

## Running

```bash
php -S localhost:8000 public/index.php
```

> You should see a greeting in the response based on your locale, as determined by the Accept-Language header, after running the project.

![Screenshot](/media/greeting-screenshot.png)

## Swagger

The following command will describe all API methods in your project:

```bash
php bin/app router:openapi:build-document
```

By default, Swagger is available at the following address:

http://localhost:8000/swagger.html

> Note that by default, there are no API methods in the project, so Swagger will notify you about this, as shown in the screenshot below.

![Screenshot](/media/swagger-screenshot.png)

## CLI

To access your project via the command line, use the following command:

```bash
php bin/app
```

The result of running this command should be something similar to the screenshot below.

![Screenshot](/media/cli-screenshot.png)

## Testing

To run the tests, use the following command:

```bash
composer test
```

## Dependencies

Your new project will be based on the following open-source solutions:

- [monolog/monolog](https://packagist.org/packages/monolog/monolog)
- [php-di/php-di](https://packagist.org/packages/php-di/php-di)
- [sunrise/coder](/docs/sunrise/coder/)
- [sunrise/http-message](/docs/sunrise/http-message/)
- [sunrise/http-router](/docs/sunrise/http-router/)
- [sunrise/hydrator](/docs/sunrise/hydrator/)
- [sunrise/translator](/docs/sunrise/translator/)
- [symfony/cache](https://packagist.org/packages/symfony/cache)
- [symfony/console](https://packagist.org/packages/symfony/console)
- [symfony/dotenv](https://packagist.org/packages/symfony/dotenv)

The development environment will also use the following open-source solutions:

- [phpstan/phpstan](https://packagist.org/packages/phpstan/phpstan)
- [phpunit/phpunit](https://packagist.org/packages/phpunit/phpunit)
- [squizlabs/php_codesniffer](https://packagist.org/packages/squizlabs/php_codesniffer)
- [vimeo/psalm](https://packagist.org/packages/vimeo/psalm)
