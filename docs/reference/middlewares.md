# Middleware Reference :id=top

## RecaptchaChallengeMiddleware

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

```php
use App\Dto\LoginRequest;
use Sunrise\Http\Router\Annotation\Middleware;
use Sunrise\Http\Router\Annotation\RequestBody;
use Sunrise\Recaptcha\Integration\Router\Middleware\RecaptchaChallengeMiddleware;

final readonly class AuthController
{
    #[Middleware(RecaptchaChallengeMiddleware::class)]
    public function login(#[RequestBody] LoginRequest $loginRequest): void
    {
    }
}
```

## RequestTerminationMiddleware

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)


