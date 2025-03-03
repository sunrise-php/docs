# sunrise/hydrator :id=top

A flexible strictly-typed hydrator.

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/hydrator/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/hydrator?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/hydrator?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/hydrator?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/hydrator?style=social)

## Installation

> If you're using [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), everything is already installed and configured for you.

```bash
composer require sunrise/hydrator
```

## Quick Start

### Object Hydration

```php
$hydrator = new \Sunrise\Hydrator\Hydrator();
$object = $hydrator->hydrate(Object::class, $data);
```

### Value Type Casting

```php
$hydrator = new \Sunrise\Hydrator\Hydrator();
$type = \Sunrise\Hydrator\Type::fromName('string');
$value = $hydrator->castValue($value, $type);
```
