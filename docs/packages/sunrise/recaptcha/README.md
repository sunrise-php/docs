# sunrise/recaptcha :id=top

Google reCAPTCHA client.

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/recaptcha/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/recaptcha?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/recaptcha?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/recaptcha?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/recaptcha?style=social)

## Installation

```bash
composer require sunrise/recaptcha
```

This package also requires [PSR-17](https://www.php-fig.org/psr/psr-17/) and [PSR-18](https://www.php-fig.org/psr/psr-18/) compatible packages;
we recommend [sunrise/http-message](/docs/packages/sunrise/http-message/) and [sunrise/http-client-curl](/docs/packages/sunrise/http-client-curl/).

```bash
composer require sunrise/http-message sunrise/http-client-curl
```

## Quick Start

```php
use Sunrise\Coder\CodecManager;
use Sunrise\Coder\Codec\UrlEncodedCodec;
use Sunrise\Http\Client\Curl\Client;
use Sunrise\Http\Message\RequestFactory;
use Sunrise\Http\Message\ResponseFactory;
use Sunrise\Hydrator\Hydrator;
use Sunrise\Recaptcha\Dto\RecaptchaVerificationRequest;
use Sunrise\Recaptcha\RecaptchaVerificationClient;
use Sunrise\Recaptcha\RecaptchaVerificationConfiguration;

// Store your 'secret' in an environment variable,
// e.g., RECAPTCHA_VERIFICATION_PRIVATE_KEY.
// https://developers.google.com/recaptcha/docs/faq
$secret = '6LeIxAcTAAAAAGG-vFI1TnRWxMZNFuojJ4WifJWe';

$client = new RecaptchaVerificationClient(
    verificationConfiguration: new RecaptchaVerificationConfiguration(privateKey: $secret),
    httpRequestFactory: new RequestFactory(),
    httpClient: new Client(new ResponseFactory()),
    codecManager: new CodecManager([new UrlEncodedCodec()]),
    hydrator: new Hydrator(),
);

$result = $client->sendRequest(new RecaptchaVerificationRequest(userToken: $token));

if ($result->success) {
    // Challenge passed...
} else {
    // Challenge failed...
}
```

## What's Next

- Refer to the [RecaptchaChallengeMiddleware](/docs/reference/middlewares.md#recaptchachallengemiddleware) middleware for token verification through the [middleware](/docs/reference/routing-annotations.md#middleware-in-the-form-of-an-fqn-class-name).
- Refer to the [RecaptchaChallenge](/docs/reference/validator-constraints.md#recaptchachallenge) constraint for token verification through the [validator](/docs/cookbook/validator-integration.md).

## Awesome Skeleton

### Integration

```php
$containerBuilder->addDefinition(
    __DIR__ . '/../vendor/sunrise/recaptcha/resources/definitions/recaptcha_verification.php',
    __DIR__ . '/../vendor/sunrise/recaptcha/resources/definitions/integration/router/middleware/recaptcha_challenge_middleware.php',
    __DIR__ . '/../vendor/sunrise/recaptcha/resources/definitions/integration/validator/constraint/recaptcha_challenge_validator.php',
);
```

### Parameters

- [recaptcha.verification.codec_context](/docs/reference/app-parameters.md#recaptcha_verification_codec_context)
- [recaptcha.verification.hydrator_context](/docs/reference/app-parameters.md#recaptcha_verification_hydrator_context)
- [recaptcha.verification.private_key](/docs/reference/app-parameters.md#recaptcha_verification_private_key)

#### RecaptchaChallengeMiddleware Parameters

- [router.recaptcha_challenge_middleware.challenge_failed_message](/docs/reference/app-parameters.md#router_recaptcha_challenge_middleware_challenge_failed_message)
- [router.recaptcha_challenge_middleware.challenge_failed_status_code](/docs/reference/app-parameters.md#router_recaptcha_challenge_middleware_challenge_failed_status_code)
- [router.recaptcha_challenge_middleware.empty_token_message](/docs/reference/app-parameters.md#router_recaptcha_challenge_middleware_empty_token_message)
- [router.recaptcha_challenge_middleware.empty_token_status_code](/docs/reference/app-parameters.md#router_recaptcha_challenge_middleware_empty_token_status_code)
- [router.recaptcha_challenge_middleware.token_header_name](/docs/reference/app-parameters.md#router_recaptcha_challenge_middleware_token_header_name)

## Tests

```bash
composer test
```
