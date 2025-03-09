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

> The example below is purely demonstrative.
> It's better to apply this middleware [globally](/docs/reference/app-parameters.md#router_route_middlewares) to all routes.
> If you're using [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), this is already handled for you.

```php
use App\Dto\PageCreateRequest;
use Sunrise\Bridge\Doctrine\Integration\Router\Middleware\RequestTerminationMiddleware;
use Sunrise\Http\Router\Annotation\Middleware;
use Sunrise\Http\Router\Annotation\RequestBody;

final readonly class PageController
{
    #[Middleware(RequestTerminationMiddleware::class)]
    public function create(#[RequestBody] PageCreateRequest $pageCreateRequest): void
    {
    }
}
```
