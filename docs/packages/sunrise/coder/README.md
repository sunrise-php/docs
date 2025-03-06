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

$codecManager = new CodecManager([
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

## Context

The **Codec Manager** abstracts specific codec implementations, meaning you do not interact with them directly.
However, there are cases where you may need to influence codec behavior directly, which can be achieved through the **context**.
There are two types of context: **global** and **operational**.

- The **global context** is set in the **constructor** of the Codec Manager or a specific codec and remains immutable throughout the application's lifecycle.
- The **operational context** is passed to each **encoding** or **decoding** operation at runtime, whether invoked via the Codec Manager or directly through a specific codec.

Below is a table of contextual keys and their descriptions.

| Key                                                               | Description                                                     |
|-------------------------------------------------------------------|-----------------------------------------------------------------|
| `\Sunrise\Coder\Codec\JsonCodec::CONTEXT_KEY_DECODING_FLAGS`      | [JSON decoding](https://www.php.net/json_decode) flags.         |
| `\Sunrise\Coder\Codec\JsonCodec::CONTEXT_KEY_DECODING_MAX_DEPTH`  | Maximum [JSON decoding](https://www.php.net/json_decode) depth. |
| `\Sunrise\Coder\Codec\JsonCodec::CONTEXT_KEY_ENCODING_FLAGS`      | [JSON encoding](https://www.php.net/json_encode) flags.         |
| `\Sunrise\Coder\Codec\JsonCodec::CONTEXT_KEY_ENCODING_MAX_DEPTH`  | Maximum [JSON encoding](https://www.php.net/json_encode) depth. |
| `\Sunrise\Coder\Codec\UrlEncodedCodec::CONTEXT_KEY_ENCODING_TYPE` | [URL encoding](https://www.php.net/http_build_query) type.      |

## Awesome Skeleton

### Integration

Integrated by default.

### Parameters

- [coder.codecs](/docs/reference/app-parameters.md#coder_codecs)
- [coder.context](/docs/reference/app-parameters.md#coder_context)
- [coder.json_codec.context](/docs/reference/app-parameters.md#coder_json_codec_context)
- [coder.url_encoded_codec.context](/docs/reference/app-parameters.md#coder_url_encoded_codec_context)

## Tests

```bash
composer test
```
