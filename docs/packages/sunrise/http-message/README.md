# sunrise/http-message :id=top

An HTTP message implementation based on [PSR-7](https://www.php-fig.org/psr/psr-7/), [PSR-17](https://www.php-fig.org/psr/psr-17/) and [RFC-7230](https://datatracker.ietf.org/doc/html/rfc7230).

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/http-message/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/http-message?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/http-message?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/http-message?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/http-message?style=social)

## Installation

> If you're using [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), everything is already installed and configured for you.

```bash
composer require sunrise/http-message
```

## PSR-7 Implementations

| Interface                                         | Implementation                               |
|---------------------------------------------------|----------------------------------------------|
| `\Psr\Http\Message\RequestInterface`              | `\Sunrise\Http\Message\Request`              |
| `\Psr\Http\Message\ResponseInterface`             | `\Sunrise\Http\Message\Response`             |
| `\Psr\Http\Message\ServerRequestInterface`        | `\Sunrise\Http\Message\ServerRequest`        |
| `\Psr\Http\Message\StreamInterface`               | `\Sunrise\Http\Message\Stream`               |
| `\Psr\Http\Message\UploadedFileInterface`         | `\Sunrise\Http\Message\UploadedFile`         |
| `\Psr\Http\Message\UriInterface`                  | `\Sunrise\Http\Message\Uri`                  |

## PSR-17 Implementations

| Interface                                         | Implementation                               |
|---------------------------------------------------|----------------------------------------------|
| `\Psr\Http\Message\RequestFactoryInterface`       | `\Sunrise\Http\Message\RequestFactory`       |
| `\Psr\Http\Message\ResponseFactoryInterface`      | `\Sunrise\Http\Message\ResponseFactory`      |
| `\Psr\Http\Message\ServerRequestFactoryInterface` | `\Sunrise\Http\Message\ServerRequestFactory` |
| `\Psr\Http\Message\StreamFactoryInterface`        | `\Sunrise\Http\Message\StreamFactory`        |
| `\Psr\Http\Message\UploadedFileFactoryInterface`  | `\Sunrise\Http\Message\UploadedFileFactory`  |
| `\Psr\Http\Message\UriFactoryInterface`           | `\Sunrise\Http\Message\UriFactory`           |

## Server Request

A request from server parameters.

```php
use Sunrise\Http\Message\ServerRequestFactory;

$request = ServerRequestFactory::fromGlobals();
```

## JSON Request

A request that encodes the provided data using `JSON` format and sets the corresponding `Content-Type` header.

> Consider using [sunrise/coder](/docs/packages/sunrise/coder/).

```php
use Sunrise\Http\Message\Request\JsonRequest;

$request = new JsonRequest('POST', '/operation', ['foo' => 'bar']);
```

## URL Encoded Request

A request that encodes the provided data using `URL Encoded` format and sets the corresponding `Content-Type` header.

> Consider using [sunrise/coder](/docs/packages/sunrise/coder/).

```php
use Sunrise\Http\Message\Request\UrlEncodedRequest;

$request = new UrlEncodedRequest('POST', '/operation', ['foo' => 'bar']);
```

## HTML Response

A response that represents an `HTML` document, ensuring the provided content is cast to a `string` and setting the corresponding `Content-Type` header.

```php
use Sunrise\Http\Message\Response\HtmlResponse;

$response = new HtmlResponse(200, '<h1>Welcome!</h1>');
```

## JSON Response

A response that encodes the provided data using `JSON` format and sets the corresponding `Content-Type` header.

> Consider using [sunrise/coder](/docs/packages/sunrise/coder/).

```php
use Sunrise\Http\Message\Response\JsonResponse;

$response = new JsonResponse(200, ['foo' => 'bar']);
```

## File Stream

```php
use Sunrise\Http\Message\Stream\FileStream;

$stream = new FileStream('/filename', 'r+b');
```

## Input Stream

A `read-only` stream wrapper for [php://input](https://www.php.net/manual/en/wrappers.php.php#wrappers.php.input).

```php
use Sunrise\Http\Message\Stream\PhpInputStream;

$stream = new PhpInputStream();
```

## Memory Stream

A stream wrapper for [php://memory](https://www.php.net/manual/en/wrappers.php.php#wrappers.php.memory).

```php
use Sunrise\Http\Message\Stream\PhpMemoryStream;

$stream = new PhpMemoryStream();
```

## Temporary Stream

A stream wrapper for [php://temp](https://www.php.net/manual/en/wrappers.php.php#wrappers.php.memory).

```php
use Sunrise\Http\Message\Stream\PhpTempStream;

$stream = new PhpTempStream();
```

## Temporary File Stream

A stream that opens a **unique temporary file** in binary read-write mode (`w+b`).

The file is **automatically deleted** when closed or when the program terminates.

```php
use Sunrise\Http\Message\Stream\TmpfileStream;

$stream = new TmpfileStream();
```

If automatic file deletion is not required, you can use another stream that also opens a **unique temporary file** in binary read-write mode (`r+b`), but **without the automatic deletion behavior**:

```php
use Sunrise\Http\Message\Stream\TempFileStream;

$stream = new TempFileStream();
```

In any case, it's useful to know that the file's URI can be gotten as follows:

```php
$uri = $stream->getMetadata('uri');
```

## Awesome Skeleton

### Integration

Integrated by default.

### Parameters

No parameters available.

## Tests

```bash
composer test
```
