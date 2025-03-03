[//]: # (TODO: Описать работу с контекстом)

# sunrise/coder :id=top

A flexible data coder for encoding and decoding formats like JSON, YAML, and more.

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/coder/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/coder?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/coder?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/coder?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/coder?style=social)

## Installation

> If you're using [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), everything is already installed and configured for you.

```bash
composer require sunrise/coder
```

## Quick Start

```php
use Sunrise\Coder\CodecManager;
use Sunrise\Coder\Codec\JsonCodec;
use Sunrise\Coder\Codec\UrlEncodedCodec;
use Sunrise\Coder\Dictionary\MediaType;

$codecManager = new CodecManager(codecs: [
    new JsonCodec(),
    new UrlEncodedCodec(),
]);

// Encoding result: {"foo": "bar"}
$codecManager->encode(MediaType::JSON, ['foo' => 'bar']);
// Decoding result: ['foo' => 'bar']
$codecManager->decode(MediaType::JSON, '{"foo": "bar"}');

// Encoding result: foo=bar
$codecManager->encode(MediaType::UrlEncoded, ['foo' => 'bar']);
// Decoding result: ['foo' => 'bar']
$codecManager->decode(MediaType::UrlEncoded, 'foo=bar');
```

## Tests

```bash
composer test
```
