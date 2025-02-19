# Awesome Skeleton

Awesome Skeleton for modern PHP 8.1+ development.

## System Requirements

PHP 8.1+

## Installation

```bash
composer create-project 'sunrise/awesome-skeleton:^4.0' awesome-app/
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
