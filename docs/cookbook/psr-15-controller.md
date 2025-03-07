# PSR-15 Controller :id=top

> Refer to the [Controller Annotation Reference](/docs/reference/controller-annotations.md) to learn about additional router features.

```php
use Psr\Http\Message\ResponseFactoryInterface;
use Psr\Http\Message\ResponseInterface;
use Psr\Http\Message\ServerRequestInterface;
use Psr\Http\Server\RequestHandlerInterface;
use Sunrise\Http\Router\Annotation\GetRoute;

#[GetRoute('example', '/example')]
final readonly class ExampleController implements RequestHandlerInterface
{
    public function __construct(
        private ResponseFactoryInterface $responseFactory,
    ) {
    }

    public function handle(ServerRequestInterface $request): ResponseInterface
    {
        return $this->responseFactory->createResponse();
    }
}
```
