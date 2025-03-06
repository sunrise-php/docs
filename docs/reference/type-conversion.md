# Type Conversion Reference :id=top

The type conversion system is provided by the [sunrise/hydrator](/docs/packages/sunrise/hydrator/) package.
It is actively used in processes such as runtime DTO initialization, runtime resolving parameters in controller actions, and more.

## Required & Optional Properties :id=required-and-optional-properties

While the logic for handling required and optional properties extends beyond type conversion, it is still an integral part of it.
Therefore, it's important to understand the following behavior: If a property is defined in a class without a default value, it must be present in the data.
Conversely, if a property has a default value, it can be omitted.

## Null

A property or parameter can accept `null` if it is marked as `nullable`.

In the type conversion system, not only `null` is considered `null`, but also, for some types, an **empty string** or a string containing **only whitespace characters**.
This behavior is implemented to support untyped data sources, such as HTML forms.

```php
public readonly ?string $foo
```

## Bool

**Expected data type**: `bool`, `string`.

A property or parameter can accept a `boolean` value if it is typed as `bool`.

As part of supporting untyped data sources, such as HTML forms, the type conversion system attempts to convert `string` values using the native PHP [Filter](https://www.php.net/manual/en/intro.filter.php) module.
As a result, a `boolean` value can be represented as a series of string values, as shown in the table below.

| **TRUE** | **FALSE** |
|----------|-----------|
| 1        | 0         |
| true     | false     |
| yes      | no        |
| on       | off       |

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly bool $foo
```

## Int

**Expected data type**: `int`, `string`.

A property or parameter can accept an `integer` value if it is typed as `int`.

As part of supporting untyped data sources, such as HTML forms, the type conversion system attempts to convert `string` values using the native PHP [Filter](https://www.php.net/manual/en/intro.filter.php) module.
Thus, an `integer` value can be represented as a [numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php).

> Remember that an `integer` in PHP is limited to the range between [PHP_INT_MIN](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-min) and [PHP_INT_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max). If you expect very large numbers, use a [string](#string) type instead.

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly int $foo
```

## Number

**Expected data type**: `int`, `float`, `string`.

A property or parameter can accept a `number` value if it is typed as `float`.

As an exception, an `integer` value will be converted to a `float`, as this is a safe process, unlike other scalar values.

As part of supporting untyped data sources, such as HTML forms, the type conversion system attempts to convert `string` values using the native PHP [Filter](https://www.php.net/manual/en/intro.filter.php) module.
Thus, an `number` value can be represented as a [numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php).

> Remember that using this type for `monetary` values may be a terrible idea, as floating-point precision in PHP is [limited](https://www.php.net/float). Instead, use a [string](#string) to avoid accidentally shooting yourself in the foot...

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly float $foo
```

## String

**Expected data type**: `int`, `string`.

A property or parameter can accept a `string` value if it is typed as `string`.

As an exception, an `integer` value will be converted to a `string`, as this is a safe process, unlike other scalar values.

```php
public readonly string $foo
```

## Array

**Expected data type**: `array`, `object`.

A property or parameter can accept an `array` or `object` if it is typed as `array`.

To type the elements of an array or object and limit their quantity, use the [Subtype](/docs/reference/hydrator-annotations.md#subtype) annotation.
Always try to use this annotation and never trust client data.

```php
public readonly array $foo
```

## Collection

**Expected data type**: `array`, `object`.

A property or parameter can accept an `array` or `object` if it is typed as a `collection`.

A `collection` is a class that implements the [ArrayAccess](https://www.php.net/manual/en/class.arrayaccess.php) interface, such as [ArrayObject](https://www.php.net/manual/en/class.arrayobject.php).
The same rules that apply to [arrays](#array) apply to such collections.

However, it is recommended to use [typed collections](/docs/cookbook/typed-collection.md) instead of regular ones.

```php
public readonly \ArrayObject $foo
```

## Enum

**Expected data type**: `int`, `string`.

A property or parameter can accept an enum case if it is typed as that enum.

The enumeration must be [backed](https://www.php.net/manual/en/class.backedenum.php) (i.e., typed) and can only use [int](#int) or [string](#string) as its type, so the same rules apply.

> Support for the [MyCLabs](https://packagist.org/packages/myclabs/php-enum) enumeration is also available, primarily for projects using PHP versions lower than [8.1](https://www.php.net/releases/8.1/en.php#enumerations).

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly Status $status
```

## Timestamp

**Expected data type**: `int`, `string`.

A property or parameter can accept a `timestamp` if it is typed as [DateTimeImmutable](https://www.php.net/manual/en/class.datetimeimmutable.php) or another class inheriting from `DateTimeImmutable` (**PHP 8 only**).

Depending on the expected timestamp format, the client will be expected to provide different data types.
If the format is `U`, an [int](#int) is expected; otherwise, a [string](#string).

The format can be overridden for a property or parameter using the [Format](/docs/reference/hydrator-annotations.md#format) annotation.
However, this should be a last resort, as the format should be defined [globally](/docs/packages/sunrise/hydrator/#context).

Just like the format, the timezone can also be overridden for a property or parameter using the [Context](/docs/reference/hydrator-annotations.md#context) annotation.
Pass an array where the key is `\Sunrise\Hydrator\Dictionary\ContextKey::TIMEZONE` and the value is the [timezone identifier](https://www.php.net/manual/en/timezones.php).
However, keep in mind that the timezone should be defined [globally](/docs/packages/sunrise/hydrator/#context).

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly \DateTimeImmutable $timestamp
```

## Timezone

**Expected data type**: `string`.

A property or parameter can accept a [timezone identifier](https://www.php.net/manual/en/timezones.php) if it is typed as [DateTimeZone](https://www.php.net/manual/en/class.datetimezone.php).

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly \DateTimeZone $timezone
```

## UID

### Ramsey UUID

**Expected data type**: `string`.

If you're using the [ramsey/uuid](https://packagist.org/packages/ramsey/uuid) package, a property or parameter can accept a `UUID` if it is typed as `\Ramsey\Uuid\UuidInterface`.

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly \Ramsey\Uuid\UuidInterface $uuid;
```

### Symfony UID

**Expected data type**: `string`.

If you are using the [symfony/uid](https://packagist.org/packages/symfony/uid) package, a property or parameter can accept a `UID` if it is typed as a class that inherits from `\Symfony\Component\Uid\AbstractUid`.

> Remember that as part of supporting untyped data sources, **empty strings** are considered [null](#null) values.

```php
public readonly \Symfony\Component\Uid\Uuid $uuid;
```

## Relationship

**Expected data type**: `array`, `object`.

A property or parameter accepts a `relationship` if it is typed as that class.

A `relationship` is a class with properties that are subject to all rules of the type conversion system.

```php
public readonly FooDto $foo
```

## Mixed

**Expected data type**: `mixed`.

A property or parameter accepts `any` value if it is typed as `mixed` or if it is not typed at all.

```php
public readonly mixed $foo
```

## Custom

Can't find the type you need?
Create a [custom type converter](/docs/cookbook/custom-type-converter.md), it's very easy!
