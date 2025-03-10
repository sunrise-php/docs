# sunrise/translator :id=top

A flexible translation manager.

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/translator/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/translator?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/translator?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/translator?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/translator?style=social)

## Installation

> If you're using [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), everything is already installed and configured for you.

```bash
composer require sunrise/translator
```

## Quick Start

```php
// This is the translation file for the locale "sr", located at "/translations/sr.php".

return [
    'Hello, {username}!' => 'Zdravo, {username}!',
];
```

```php
use Sunrise\Translator\TranslatorManager;
use Sunrise\Translator\Translator\DirectoryTranslator;

$translator = new TranslatorManager([
    new DirectoryTranslator(domain: 'app', directory: '/translations'),
]);

// Translating result: Zdravo, Marko!
$translator->translate(domain: 'app', locale: 'sr', template: 'Hello, {username}!', placeholders: [
    '{username}' => 'Marko',
]);
```

## Awesome Skeleton

### Integration

Integrated by default.

### Parameters

- [translator.translators](/docs/reference/app-parameters.md#translator_translators)

## Tests

```bash
composer test
```
