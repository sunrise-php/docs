# Hydrator Annotation Reference

## Alias

Allows associating a dataset non-normalized key with a property when its name cannot match the key.

For example, the [reCAPTCHA](https://developers.google.com/recaptcha/docs/verify#api-response) returns a list of error codes with the key `error-codes`, but in PHP, a property cannot have this name. To fix this, you can use this annotation.

```php
use Sunrise\Hydrator\Annotation\Alias;
use Sunrise\Hydrator\Annotation\Subtype;

#[Alias('error-codes')]
#[Subtype('string')]
public readonly array $errorCodes
```

## Context

Allows passing [additional context](/docs/reference/app-parameters.md#hydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/).

> Pay attention to the `\Sunrise\Hydrator\Dictionary\ContextKey` dictionary.

```php
use Sunrise\Hydrator\Annotation\Context;

#[Context([])]
public readonly string $foo
```

## DefaultValue

Allows setting a default value for a property when it cannot be done directly.

For example, a [non-promoted](https://www.php.net/manual/en/language.oop5.decon.php#language.oop5.decon.constructor.promotion) [readonly](https://www.php.net/manual/en/language.oop5.properties.php#language.oop5.properties.readonly-properties) property cannot have a default value.

> A property with this annotation is [optional](/docs/reference/type-conversion.md#required-and-optional-properties).

```php
use Sunrise\Hydrator\Annotation\DefaultValue;

#[DefaultValue(null)]
public readonly ?string $foo
```

## Format

Allows specifying a data format.

> You can set the global date and time format through the [hydrator.context.timestamp_format](/docs/reference/app-parameters.md#hydrator_context_timestamp_format) parameter.

```php
use DateTimeImmutable;
use Sunrise\Hydrator\Annotation\Format;

#[Format('U')] // expects a Unix timestamp...
public readonly DateTimeImmutable $timestamp
```

## Ignore

Allows ignoring a property during hydration.

```php
use DateTimeImmutable;
use Sunrise\Hydrator\Annotation\Ignore;

#[Ignore]
public readonly DateTimeImmutable $createdAt = new DateTimeImmutable()
```

## MapEntity

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

Allows binding a requested entity to a property.

**Always explicitly specify the [subtype](#subtype) for a value in a dataset to avoid unexpected behavior.**

> By default, the entity will be found using the [primary key](https://www.doctrine-project.org/projects/doctrine-orm/en/3.3/tutorials/composite-primary-keys.html). However, if you need to change the field used for the find, specify the field name in the `field` parameter of this annotation.

> If you need to specify [additional criteria](https://www.doctrine-project.org/projects/doctrine-orm/en/3.3/reference/working-with-objects.html#by-criteria) for finding the entity, you can do so by setting them in the `criteria` parameter of this annotation.

> By default, the [default entity manager](/docs/reference/app-parameters.md#hydrator_map_entity_type_converter_default_entity_manager_name) will be used. If you need to change it, specify the desired entity manager's name in the `em` parameter of this annotation.

> If you need to bind an [array](/docs/reference/type-conversion.md#array) or [collection](/docs/reference/type-conversion.md#collection) of entities to a property, you can easily do this by setting the entity as the [subtype](#subtype) of that array or collection.

```php
use App\Entity\Category;
use Sunrise\Bridge\Doctrine\Integration\Hydrator\Annotation\MapEntity;
use Sunrise\Hydrator\Annotation\Alias;
use Sunrise\Hydrator\Annotation\Subtype;
use Sunrise\Hydrator\Dictionary\BuiltinType;

#[Alias('categoryId')]
#[Subtype(BuiltinType::STRING)]
#[MapEntity]
public readonly Category $category;
```

## Subtype

Allows typing [arrays](/docs/reference/type-conversion.md#array) and [collections](/docs/reference/type-conversion.md#collection) with the option to limit the number of elements to prevent memory leaks.

> The subtype can be anything that a property or parameter can have as a type, we recommend reviewing the [type conversion system](/docs/reference/type-conversion.md) to better understand the typing process.

> If the [array](/docs/reference/type-conversion.md#array) or [collection](/docs/reference/type-conversion.md#collection) element can be [null](/docs/reference/type-conversion.md#null), specify this in the `allowsNull` parameter of this annotation.

> Pay attention to the `\Sunrise\Hydrator\Dictionary\BuiltinType` dictionary.

```php
use Sunrise\Hydrator\Annotation\Subtype;

#[Subtype(BuiltinType::STRING, limit: 100)]
public readonly array $tags
```
