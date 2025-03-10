# Routing Syntax Reference :id=top

## Optional Parts

To define a part of the route as optional, enclose it in parentheses.

> Note that nested optional parts are not supported.

> Note that an optional part can contain only one [variable](#route-variables).

> Refer to the [Routing Annotation Reference](/docs/reference/routing-annotations.md) to learn more about the [router](/docs/packages/sunrise/http-router/)'s features.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.posts.list', '(/api)/posts')]
public function list(): void
```

_Demonstration of an operation accessible via both the `/api/posts` and `/posts` paths._

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.list', '/api/posts(/{language})')]
public function list(#[RequestVariable] string $language = 'en'): void
```

_Demonstration of an operation accessible via both the `/api/posts/sr` and `/api/posts` paths._

## Route Variables

To define a variable in the route, enclose its name in curly braces.

> Note that multiple variables cannot be defined within an [optional part](#optional-parts).

> Note that the variable name must be unique within the route.

> Note that the variable name must match the [PCRE Named Subpattern](https://www.pcre.org/original/doc/html/pcrepattern.html#SEC16).

> Refer to the [Routing Annotation Reference](/docs/reference/routing-annotations.md) to learn more about the [router](/docs/packages/sunrise/http-router/)'s features.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.read', '/api/posts/{slug}')]
public function read(#[RequestVariable] string $slug): void
```

## Variable Patterns

To define a [variable](#route-variables) pattern, specify it after its name in angle brackets.

**Expects not a regex, but a subpattern, i.e., an expression without delimiters and modifiers.**

> Note the [alternative way](/docs/reference/routing-annotations.md#pattern) of defining the pattern.

> Note that the `#` symbol is reserved and cannot be used in the pattern.

> Note that since angle brackets are used to define the pattern, they cannot be used inside it.
> Named subpatterns can be defined using an [alternative syntax](https://www.php.net/manual/en/regexp.reference.subpatterns.php) with single quotes.

> Refer to the [Routing Annotation Reference](/docs/reference/routing-annotations.md) to learn more about the [router](/docs/packages/sunrise/http-router/)'s features.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.read', '/api/posts/{slug<[-0-9a-z]{1,255}>}')]
public function read(#[RequestVariable] string $slug): void
```
