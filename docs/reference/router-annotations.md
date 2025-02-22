# Router Annotations

## ApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an API operation.

You might want to use one of the following annotations: [DeleteApiRoute](#deleteapiroute), [GetApiRoute](#getapiroute), [HeadApiRoute](#headapiroute), [OptionsApiRoute](#optionsapiroute), [PatchApiRoute](#patchapiroute), [PatchApiRoute](#patchapiroute), [PostApiRoute](#postapiroute), [PurgeApiRoute](#purgeapiroute), [PutApiRoute](#putapiroute).

The following annotations may be useful for you: [Method](#method), [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\ApiRoute;

#[ApiRoute('api.operations.test', '/api/operations/test', 'GET')]
public function test(): void
```

## Constraint

Sets constraints on action parameters, for example, they can be validated using Symfony Validator Constraints.

Works out-of-the-box with the following annotations: [RequestCookie](#RequestCookie), [RequestHeader](#RequestHeader), [RequestVariable](#RequestVariable).

```php
use Sunrise\Http\Router\Annotation\Constraint;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestHeader;
use Symfony\Component\Validator\Constraints\Length;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
public function test(
    #[RequestHeader('x-foo')]
    #[Constraint(new Length(max: 255))]
    string $foo,
): void
```

## Consumes

Sets the media type(s) consumed by an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use App\Dictionary\MediaType;
use App\Dto\User\UserCreateRequest;
use Sunrise\Http\Router\Annotation\Consumes;
use Sunrise\Http\Router\Annotation\PostApiRoute;
use Sunrise\Http\Router\Annotation\RequestBody;

#[PostApiRoute('api.users.create', '/api/users')]
#[Consumes(MediaType::JSON)]
public function create(
    #[RequestBody] UserCreateRequest $userCreateRequest,
): void
```

## DefaultAttribute

Sets the default value for a request attribute.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\DefaultAttribute;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.publications.list', '/api/publications(/{language})')]
#[DefaultAttribute('language', 'en')]
public function list(
    #[RequestVariable] string $language,
): void
```

## DeleteApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a DELETE API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\DeleteApiRoute;

#[DeleteApiRoute('api.operations.test', '/api/operations/test')]
public function test(): void
```

## DeleteMethod

Sets the DELETE HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\DeleteMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[DeleteMethod]
public function test(): void
```

## DeleteRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a DELETE operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\DeleteRoute;

#[DeleteRoute('test', '/test')]
public function test(): void
```

## Deprecated

Marks an operation as deprecated.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\Deprecated;
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Deprecated]
public function test(): void
```

## Description

Sets the description for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\Description;
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Description('Lorem ipsum dolor sit amet...')]
public function test(): void
```

## EncodableResponse

Specifies to encode views returned directly from an operation.

The following annotations may be useful for you: [ResponseStatus](#responsestatus).

```php
use App\Dictionary\MediaType;
use App\View\User\UserView;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.users.read', '/api/users/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestVariable] int $id): UserView
```

## GetApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a GET API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
public function test(): void
```

## GetMethod

Sets the GET HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\GetMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[GetMethod]
public function test(): void
```

## GetRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a GET operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\GetRoute;

#[GetRoute('test', '/test')]
public function test(): void
```

## HeadApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a HEAD API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\HeadApiRoute;

#[HeadApiRoute('test', '/test')]
public function test(): void
```

## HeadMethod

Sets the HEAD HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\HeadMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[HeadMethod]
public function test(): void
```

## HeadRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a HEAD operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\HeadRoute;

#[HeadRoute('test', '/test')]
public function test(): void
```

## Method

Sets the HTTP method(s) for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\Method;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[Method('GET')]
public function test(): void
```

## Middleware

Sets middleware(s) for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: A reference to middleware can be an FQN class name or a callable notation.

### Middleware in the form of an FQN class name

```php
use App\Middleware\FooMiddleware;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Middleware;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Middleware(FooMiddleware::class)]
public function test(): void
```

### Middleware in the form of a callable notation

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Middleware;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Middleware([self::class, 'process'])]
public function test(): void
```

## NamePrefix

Sets a prefix for an operation name.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\NamePrefix;

#[NamePrefix('api.operations.')]
final class TestController
{
    #[GetApiRoute('test', '/api/operations/test')]
    public function test(): void
    {
    }
}
```

## Operation

Allows you to manually document an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> ❗ **Important**: Do not overuse this annotation.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\OpenApi\Annotation\Operation;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Operation([
    'externalDocs' => [
        'url' => 'https://example.com/',
    ],
])]
public function test(): void
```

## OptionsApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an OPTIONS API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\OptionsApiRoute;

#[OptionsApiRoute('test', '/test')]
public function test(): void
```

## OptionsMethod

Sets the OPTIONS HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\OptionsMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[OptionsMethod]
public function test(): void
```

## OptionsRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an OPTIONS operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\OptionsRoute;

#[OptionsRoute('test', '/test')]
public function test(): void
```

## PatchApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a PATCH API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PatchApiRoute;

#[PatchApiRoute('test', '/test')]
public function test(): void
```

## PatchMethod

Sets the PATCH HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PatchMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[PatchMethod]
public function test(): void
```

## PatchRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a PATCH operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PatchRoute;

#[PatchRoute('test', '/test')]
public function test(): void
```

## PathPostfix

Sets a postfix for an operation path.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\PathPostfix;

#[PathPostfix('.json')]
final class TestController
{
    #[GetApiRoute('api.operations.test', '/api/operations/test')]
    public function test(): void
    {
    }
}
```

## PathPrefix

Sets a prefix for an operation path.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\PathPrefix;

#[PathPrefix('/api/operations')]
final class TestController
{
    #[GetApiRoute('api.operations.test', '/test')]
    public function test(): void
    {
    }
}
```

## Pattern

Sets a pattern for a route variable.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: You can also specify the pattern directly in the route – `{id<\d+>}`.

> ❗ **Important**: Specify not a Regular Expression, but a subpattern, i.e., an expression without delimiters and modifiers.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Pattern;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.user.read', '/api/user/{id}')]
#[Pattern('id', '[0-9]+')]
public function read(#[RequestVariable] int $id): void
```

## PostApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a POST API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PostApiRoute;

#[PostApiRoute('test', '/test')]
public function test(): void
```

## PostMethod

Sets the POST HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PostMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[PostMethod]
public function test(): void
```

## PostRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a POST operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PostRoute;

#[PostRoute('test', '/test')]
public function test(): void
```

## Priority

Sets the priority for a route.

This rare annotation is used to assign a priority to a route. Avoid using it within a single project. It is intended for extending the router's functionality, such as when a provider supplies routes and you need to override them in your project.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: This annotation allows you to override Swagger and OpenAPI document routes.

> ❗ **Important**: Do not overuse this annotation.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Priority;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Priority(1)]
public function test(): void
```

## Produces

Sets the media type(s) produced by an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use App\Dictionary\MediaType;
use App\View\User\UserView;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.users.read', '/api/users/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestVariable] int $id): UserView
```

## PurgeApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a PURGE API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PurgeApiRoute;

#[PurgeApiRoute('test', '/test')]
public function test(): void
```

## PurgeMethod

Sets the PURGE HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PurgeMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[PurgeMethod]
public function test(): void
```

## PurgeRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a PURGE operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PurgeRoute;

#[PurgeRoute('test', '/test')]
public function test(): void
```

## PutApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a PUT API operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PutApiRoute;

#[PutApiRoute('test', '/test')]
public function test(): void
```

## PutMethod

Sets the PUT HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PutMethod;

#[ApiRoute('api.operations.test', '/api/operations/test')]
#[PutMethod]
public function test(): void
```

## PutRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a PUT operation.

The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PutRoute;

#[PutRoute('test', '/test')]
public function test(): void
```

## RequestBody

Used to bind a request body to an operation parameter.

```php
use App\Dictionary\MediaType;
use App\Dto\User\UserCreateRequest;
use Sunrise\Http\Router\Annotation\Consumes;
use Sunrise\Http\Router\Annotation\PostApiRoute;
use Sunrise\Http\Router\Annotation\RequestBody;

#[PostApiRoute('api.users.create', '/api/users')]
#[Consumes(MediaType::JSON)]
public function create(
    #[RequestBody] UserCreateRequest $userCreateRequest,
): void
```

## RequestCookie

Used to bind a request cookie to an operation parameter.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestCookie;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
public function test(#[RequestCookie('foo')] string $foo): void
```

## RequestHeader

Used to bind a request header to an operation parameter.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestHeader;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
public function test(#[RequestHeader('X-Foo')] string $foo): void
```

## RequestQuery

Used to bind a request query to an operation parameter.

```php
use App\Dto\User\UserSearchRequest;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestQuery;

#[GetApiRoute('api.users.list', '/api/users')]
public function list(#[RequestQuery] UserSearchRequest $userSearchRequest): void
```

## RequestVariable

Used to bind a route variable to an operation parameter.

```php
use App\Dictionary\MediaType;
use App\View\User\UserView;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.users.read', '/api/users/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestVariable] int $id): UserView
```

## ResponseHeader

Sets a response header.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\ResponseHeader;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[ResponseHeader('X-Foo', 'foo')]
public function test(): void
```

## ResponseStatus

Sets a response status.

```php
use App\Dictionary\MediaType;
use App\Dto\User\UserCreateRequest;
use App\View\User\UserView;
use Sunrise\Http\Router\Annotation\Consumes;
use Sunrise\Http\Router\Annotation\PostApiRoute;
use Sunrise\Http\Router\Annotation\RequestBody;
use Sunrise\Http\Router\Annotation\ResponseStatus;

#[PostApiRoute('api.users.create', '/api/users')]
#[Consumes(MediaType::JSON)]
#[ResponseStatus(201)]
public function create(
    #[RequestBody] UserCreateRequest $userCreateRequest,
): UserView
```

## Route

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an operation.

You might want to use one of the following annotations: [DeleteRoute](#deleteroute), [GetRoute](#getroute), [HeadRoute](#headroute), [OptionsRoute](#optionsroute), [PatchRoute](#patchroute), [PatchRoute](#patchroute), [PostRoute](#postroute), [PurgeRoute](#purgeroute), [PutRoute](#putroute).

The following annotations may be useful for you: [Method](#method), [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\Route;

#[Route('test', '/test', methods: ['GET'])]
public function test(): void
```

## Summary

Sets the summary for an operation

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Summary;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Summary('Lorem Ipsum...')]
public function test(): void
```

## Tag

Adds tag(s) for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Tag;

#[GetApiRoute('api.operations.test', '/api/operations/test')]
#[Tag('foo')]
public function test(): void
```
