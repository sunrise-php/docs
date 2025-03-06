[//]: # (TODO: curlMultiSelectTimeout; curlMultiSelectSleepDuration)

# sunrise/http-client-curl :id=top

A simple cURL client implementing [PSR-18](https://www.php-fig.org/psr/psr-18/).

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/http-client-curl/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/http-client-curl?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/http-client-curl?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/http-client-curl?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/http-client-curl?style=social)

## Installation

```bash
composer require sunrise/http-client-curl
```

This package also requires a [PSR-17](https://www.php-fig.org/psr/psr-17/) compatible package;
we recommend [sunrise/http-message](/docs/packages/sunrise/http-message/).

```bash
composer require sunrise/http-message
```

## Quick Start

### Single Request

```php
use Sunrise\Http\Client\Curl\Client;
use Sunrise\Http\Message\RequestFactory;
use Sunrise\Http\Message\ResponseFactory;

$client = new Client(new ResponseFactory());
$requestFactory = new RequestFactory();

$request = $requestFactory->createRequest('GET', 'https://www.php.net/');
$response = $client->sendRequest($request);
```

### Multiple Requests

```php
use Sunrise\Http\Client\Curl\Client;
use Sunrise\Http\Client\Curl\MultiRequest;
use Sunrise\Http\Message\RequestFactory;
use Sunrise\Http\Message\ResponseFactory;

$client = new Client(new ResponseFactory());
$requestFactory = new RequestFactory();

$requests = [
    $requestFactory->createRequest('GET', 'https://www.php.net/releases/8.4/en.php'),
    $requestFactory->createRequest('GET', 'https://www.php.net/releases/8.3/en.php'),
];

$multiRequest = new MultiRequest(...$requests);
$multiResponse = $client->sendRequest($multiRequest);

// Responses with the same keys as the requests.
$responses = $multiResponse->getResponses();
```

## cURL Options

The following options cannot be overridden:

- [CURLOPT_CUSTOMREQUEST](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-customrequest)
- [CURLOPT_HEADER](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-header)
- [CURLOPT_HTTPHEADER](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-httpheader)
- [CURLOPT_POSTFIELDS](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-postfields)
- [CURLOPT_RETURNTRANSFER](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-returntransfer)
- [CURLOPT_URL](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-url)

```php
$client = new Client(new ResponseFactory(), curlOptions: [
    \CURLOPT_AUTOREFERER => true,
    \CURLOPT_FOLLOWLOCATION => true,
]);
```

## Awesome Skeleton

### Integration

```php
$containerBuilder->addDefinitions(
    __DIR__ . '/../vendor/sunrise/http-client-curl/resources/definitions/client.php',
);
```

### Parameters

- [curl.options](/docs/reference/app-parameters.md#curl_options)
- [curl.multi_select_timeout](/docs/reference/app-parameters.md#curl_multi_select_timeout)
- [curl.multi_select_sleep_duration](/docs/reference/app-parameters.md#curl_multi_select_sleep_duration)

## Tests

```bash
composer test
```
