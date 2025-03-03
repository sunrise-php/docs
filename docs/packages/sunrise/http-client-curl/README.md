[//]: # (TODO: Описать опции curlMultiSelectTimeout и curlMultiSelectSleepDuration)

# sunrise/http-client-curl :id=top

A simple HTTP cURL client implementing [PSR-18](https://www.php-fig.org/psr/psr-18/).

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/http-client-curl/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/http-client-curl?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/http-client-curl?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/http-client-curl?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/http-client-curl?style=social)

## Installation

```bash
composer require sunrise/http-client-curl
```

## Quick Start

To work with the HTTP client, an implementation of the HTTP message is required.
We recommend using [sunrise/http-message](/docs/packages/sunrise/http-message/), but you can use any other [PSR-7](https://www.php-fig.org/psr/psr-7/) compatible implementation.

```bash
composer require sunrise/http-message
```

Now we can initialize the HTTP client.
Note that when initializing, we can pass [cURL parameters](https://www.php.net/manual/en/curl.constants.php), but this is optional.

```php
use Sunrise\Http\Client\Curl\Client;
use Sunrise\Http\Message\ResponseFactory;

$client = new Client(new ResponseFactory(), [
    \CURLOPT_AUTOREFERER => true,
    \CURLOPT_FOLLOWLOCATION => true,
]);
```

Now we can send an HTTP request.
Let's request the homepage of [php.net](https://www.php.net/).

```php
$response = $client->sendRequest((new RequestFactory())->createRequest('GET', 'https://www.php.net/'));
```

If we need to send multiple requests simultaneously, it's very easy to do.

```php
$multiResponse = $client->sendRequest(
    new MultiRequest(
        php82: (new RequestFactory())->createRequest('GET', 'https://www.php.net/releases/8.2/en.php'),
        php83: (new RequestFactory())->createRequest('GET', 'https://www.php.net/releases/8.3/en.php'),
        php84: (new RequestFactory())->createRequest('GET', 'https://www.php.net/releases/8.4/en.php'),
    )
);

// Response from: https://www.php.net/releases/8.2/en.php
$php82Response = $multiResponse->getResponses()['php82'];
// Response from: https://www.php.net/releases/8.3/en.php
$php83Response = $multiResponse->getResponses()['php83'];
// Response from: https://www.php.net/releases/8.4/en.php
$php84Response = $multiResponse->getResponses()['php84'];
```

_Note that in this example, you have the option to assign a name to each request so that you can later reference the responses associated with them, but this is an optional feature._

## Awesome Skeleton

For integration with [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), open the `config/container.php` configuration file and place the following code somewhere in it.

```php
$containerBuilder->addDefinitions(
    __DIR__ . '/../vendor/sunrise/http-client-curl/resources/definitions/client.php',
);
```

Now you can use this client as `\Psr\Http\Client\ClientInterface` through dependency injection.

You can also override the following parameters:

- [curl.options](/docs/reference/app-parameters.md#curl_options)
- [curl.multi_select_timeout](/docs/reference/app-parameters.md#curl_multi_select_timeout)
- [curl.multi_select_sleep_duration](/docs/reference/app-parameters.md#curl_multi_select_sleep_duration)

## Tests

```bash
composer test
```
