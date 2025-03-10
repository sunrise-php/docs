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
use Sunrise\Hydrator\Exception\InvalidDataException;
use Sunrise\Hydrator\Hydrator;

$hydrator = new Hydrator();

try {
    $object = $hydrator->hydrate(SomeDto::class, $data);
} catch (InvalidDataException $e) {
    // A list of user-friendly errors that support translation.
    $errors = $e->getExceptions();
}
```

### Object Hydration from JSON

> Consider using [sunrise/coder](/docs/packages/sunrise/coder/).

```php
use Sunrise\Hydrator\Exception\InvalidDataException;
use Sunrise\Hydrator\Hydrator;

$hydrator = new Hydrator();

try {
    // Yes, the name of this method isn't the most logical, but that's just how it is...
    $object = $hydrator->hydrateWithJson(SomeDto::class, $json);
} catch (InvalidDataException $e) {
    // A list of user-friendly errors that support translation.
    $errors = $e->getExceptions();
}
```

### Value Casting

```php
use Sunrise\Hydrator\Dictionary\BuiltinType;
use Sunrise\Hydrator\Exception\InvalidDataException;
use Sunrise\Hydrator\Exception\InvalidValueException;
use Sunrise\Hydrator\Hydrator;
use Sunrise\Hydrator\Type;

$hydrator = new Hydrator();

try {
    // Casting result: int(42)
    $value = $hydrator->castValue('42', Type::fromName(BuiltinType::INT));
} catch (InvalidDataException $e) {
    // A list of user-friendly errors that support translation.
    $errors = $e->getExceptions();
} catch (InvalidValueException $e) {
    // This exception is a user-friendly error that support translation.
}
```

## Context

The **Hydrator** uses type converters that you do not interact with directly.
However, there are cases where you may need to influence their behavior, which can be done through **context**.
There are two types of context: **global** and **operational**.

- The **global context** is defined in the **constructor** of either the Hydrator or a specific type converter and remains immutable throughout the application's lifecycle.
- The **operational context** is assigned at runtime for each operation, specifically during **object hydration** and **value casting**.

Below is a table of contextual keys along with their descriptions.

| Key                                                         | Description                                         |
|-------------------------------------------------------------|-----------------------------------------------------|
| `\Sunrise\Hydrator\Dictionary\ContextKey::TIMESTAMP_FORMAT` | Expected date and time format.                      |
| `\Sunrise\Hydrator\Dictionary\ContextKey::TIMEZONE`         | Time zone used during date and time initialization. |

## What's Next :id=what-is-next

- Refer to the [Hydrator Annotation Reference](/docs/reference/hydrator-annotations.md) to learn about the additional features of the **Hydrator**.
- Refer to the [Type Conversion Reference](/docs/reference/type-conversion.md) to learn how the **Hydrator** handles types.
- Refer to the [Custom Type Converter](/docs/cookbook/custom-type-converter.md) example if you want to learn how to extend the **Hydrator** on your own.

## Awesome Skeleton

### Integration

Integrated by default.

### Parameters

- [hydrator.context](/docs/reference/app-parameters.md#hydrator_context)
- [hydrator.context.timestamp_format](/docs/reference/app-parameters.md#hydrator_context_timestamp_format)
- [hydrator.context.timezone_identifier](/docs/reference/app-parameters.md#hydrator_context_timezone_identifier)
- [hydrator.type_converters](/docs/reference/app-parameters.md#hydrator_type_converters)

## Doctrine Annotations

If, for any reason, you cannot use [PHP attributes](https://www.php.net/manual/en/language.attributes.overview.php) but need to use the [additional features](/docs/reference/hydrator-annotations.md) of the Hydrator, you can use [Doctrine annotations](https://www.doctrine-project.org/projects/doctrine-annotations/en/2.0/index.html) instead.

```bash
composer require doctrine/annotations
```

```php
use Sunrise\Hydrator\AnnotationReader\DoctrineAnnotationReader;

$hydrator->setAnnotationReader(DoctrineAnnotationReader::default());
```

## Tests

```bash
composer test
```
