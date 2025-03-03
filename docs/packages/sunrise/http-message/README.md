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

## PSR-7 and PSR-17

Primarily, this package includes [PSR-7](https://www.php-fig.org/psr/psr-7/) and [PSR-17](https://www.php-fig.org/psr/psr-17/) implementations,
so let's define the mapping with the corresponding implementations.

| Interface                                         | Implementation                               |
|---------------------------------------------------|----------------------------------------------|
| `\Psr\Http\Message\RequestFactoryInterface`       | `\Sunrise\Http\Message\RequestFactory`       |
| `\Psr\Http\Message\RequestInterface`              | `\Sunrise\Http\Message\Request`              |
| `\Psr\Http\Message\ResponseFactoryInterface`      | `\Sunrise\Http\Message\ResponseFactory`      |
| `\Psr\Http\Message\ResponseInterface`             | `\Sunrise\Http\Message\Response`             |
| `\Psr\Http\Message\ServerRequestFactoryInterface` | `\Sunrise\Http\Message\ServerRequestFactory` |
| `\Psr\Http\Message\ServerRequestInterface`        | `\Sunrise\Http\Message\ServerRequest`        |
| `\Psr\Http\Message\StreamFactoryInterface`        | `\Sunrise\Http\Message\StreamFactory`        |
| `\Psr\Http\Message\StreamInterface`               | `\Sunrise\Http\Message\Stream`               |
| `\Psr\Http\Message\UploadedFileFactoryInterface`  | `\Sunrise\Http\Message\UploadedFileFactory`  |
| `\Psr\Http\Message\UploadedFileInterface`         | `\Sunrise\Http\Message\UploadedFile`         |
| `\Psr\Http\Message\UriFactoryInterface`           | `\Sunrise\Http\Message\UriFactory`           |
| `\Psr\Http\Message\UriInterface`                  | `\Sunrise\Http\Message\Uri`                  |

## Server Request

```php
$request = \Sunrise\Http\Message\ServerRequestFactory::fromGlobals();
```

## JSON Request

```php
$request = new \Sunrise\Http\Message\Request\JsonRequest('POST', '/', ['foo' => 'bar']);
```

## URL Encoded Request

```php
$request = new \Sunrise\Http\Message\Request\UrlEncodedRequest('POST', '/', ['foo' => 'bar']);
```

## HTML Response

```php
$response = new \Sunrise\Http\Message\Response\HtmlResponse(200, '<h1>Welcome!</h1>');
```

## JSON Response

```php
$response = new \Sunrise\Http\Message\Response\JsonResponse(200, ['foo' => 'bar']);
```

## File Stream

```php
$stream = new \Sunrise\Http\Message\Stream\FileStream('/filename', 'r+b');
```

## Input Stream

More information related to this stream can be found [here](https://www.php.net/manual/en/wrappers.php.php).

```php
$stream = new \Sunrise\Http\Message\Stream\PhpInputStream();
```

## Memory Stream

More information related to this stream can be found [here](https://www.php.net/manual/en/wrappers.php.php).

```php
$stream = new \Sunrise\Http\Message\Stream\PhpMemoryStream();
```

## Temporary Stream

More information related to this stream can be found [here](https://www.php.net/manual/en/wrappers.php.php).

```php
$stream = new \Sunrise\Http\Message\Stream\PhpTempStream();
```

## Temporary File Stream

The stream opens a unique temporary file in binary read/write mode (w+b).
The file will be automatically deleted when it is closed or when the program terminates.

```php
$stream = new \Sunrise\Http\Message\Stream\TmpfileStream();
```

If you don't require the behavior described above, you can use an alternative temporary file stream:

```php
$stream = new \Sunrise\Http\Message\Stream\TempFileStream();
```

If you need to get the file path, you can do it as follows:

```php
$filename = $stream->getMetadata('uri');
```

## Tests

```bash
composer test
```
