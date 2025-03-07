# Validator Integration :id=top

[Symfony Validator](https://symfony.com/doc/current/validation.html) is commonly used in the **Sunrise ecosystem**.
If it's not installed, install it with:

```bash
composer require symfony/validator
```

If you are using [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), integrate the **validator** as follows:

```php
$containerBuilder->addDefinitions(
    __DIR__ . '/../vendor/sunrise/http-router/resources/definitions/bridges/symfony/validator.php',
);
```
