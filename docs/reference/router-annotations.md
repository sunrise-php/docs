# Router Annotations

## ApiRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an API operation.

> 💡 **Tip**: You may want to use one of the following annotations: [DeleteApiRoute](#deleteapiroute), [GetApiRoute](#getapiroute), [HeadApiRoute](#headapiroute), [OptionsApiRoute](#optionsapiroute), [PatchApiRoute](#patchapiroute), [PatchApiRoute](#patchapiroute), [PostApiRoute](#postapiroute), [PurgeApiRoute](#purgeapiroute), [PutApiRoute](#putapiroute).

> 💡 **Tip**: The following annotations may be useful for you: [Method](#method), [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

> 💡 **Tip**: Pay attention to the `ApiRoute::METHOD_*` annotation constants.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;

#[ApiRoute('api.operations.example', '/api/operations/example', 'GET')]
public function example(): void
```

## Constraint

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets constraints on action parameters, for example, they can be validated using Symfony Validator Constraints.

> 💡 **Tip**: This annotation works out-of-the-box with the following annotations: [RequestCookie](#RequestCookie), [RequestHeader](#RequestHeader), [RequestVariable](#RequestVariable).

```php
use Sunrise\Http\Router\Annotation\Constraint;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestHeader;
use Symfony\Component\Validator\Constraints\Length;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
public function example(
    #[RequestHeader('x-foo')]
    #[Constraint(new Length(max: 255))]
    string $foo,
): void
```

## Consumes

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

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

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

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

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `DELETE` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\DeleteApiRoute;

#[DeleteApiRoute('api.operations.example', '/api/operations/example')]
public function example(): void
```

## DeleteMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `DELETE` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\DeleteMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[DeleteMethod]
public function example(): void
```

## DeleteRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `DELETE` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\DeleteRoute;

#[DeleteRoute('example', '/example')]
public function example(): void
```

## Deprecated

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks an operation as deprecated.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\Deprecated;
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Deprecated]
public function example(): void
```

## Description

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the description for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: Use multiple annotations if the description is too long, and the router will combine them into one.

```php
use Sunrise\Http\Router\Annotation\Description;
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Description('Lorem ipsum dolor sit amet...')]
public function example(): void
```

## EncodableResponse

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Specifies to encode views returned directly from an operation.

> 💡 **Tip**: The following annotations may be useful for you: [ResponseStatus](#responsestatus).

> 💡 **Tip**: If you need to override the [default media type](/docs/reference/parameters.md#routerencodable_response_resolverdefault_media_type), set it using the `defaultMediaType` parameter of the annotation.

> 💡 **Tip**: If you need to pass [additional context](/docs/reference/parameters.md#routerencodable_response_resolvercodec_context) to the [encoder](/docs/packages/sunrise/coder/), set it through the `codecContext` parameter of the annotation.

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

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `GET` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
public function example(): void
```

## GetMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `GET` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\GetMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[GetMethod]
public function example(): void
```

## GetRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `GET` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\GetRoute;

#[GetRoute('example', '/example')]
public function example(): void
```

## HeadApiRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `HEAD` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\HeadApiRoute;

#[HeadApiRoute('example', '/example')]
public function example(): void
```

## HeadMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `HEAD` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\HeadMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[HeadMethod]
public function example(): void
```

## HeadRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `HEAD` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\HeadRoute;

#[HeadRoute('example', '/example')]
public function example(): void
```

## Method

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the HTTP method(s) for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: Pay attention to the `Method::METHOD_*` constants.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\Method;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[Method('GET')]
public function example(): void
```

## Middleware

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets middleware(s) for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: A reference to middleware can be an [FQN class name](#middleware-in-the-form-of-an-fqn-class-name) or a [callable notation](#middleware-in-the-form-of-a-callable-notation).

### Middleware in the form of an FQN class name

```php
use App\Middleware\ExampleMiddleware;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Middleware;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Middleware(ExampleMiddleware::class)]
public function example(): void
```

### Middleware in the form of a callable notation

> 💡 **Tip**: Note that middleware can be part of your controller. This can sometimes be useful, but **avoid overusing it**.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Middleware;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Middleware([self::class, 'middleware'])]
public function example(): void
```

## NamePrefix

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets a prefix for an operation name.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: Think twice before using this annotation in your project. It may lead to confusion when a QA engineer, front-end developer, or another team member asks about an operation. Instead of easily searching for the controller, you might end up unraveling a web of annotations. **Overusing this annotation can potentially cause more harm than good**.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\NamePrefix;

#[NamePrefix('api.operations.')]
final class ExampleController
{
    #[GetApiRoute('example', '/api/operations/example')]
    public function example(): void
    {
    }
}
```

## Operation

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Allows you to manually document an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip:** If you need to set a global rule, it's better to use the [router.openapi.initial_document](/docs/reference/parameters.md#routeropenapiinitial_document) parameter.

> ❗ **Important**: Do not overuse this annotation.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\OpenApi\Annotation\Operation;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Operation([
    'externalDocs' => [
        'url' => 'https://example.com/',
    ],
])]
public function example(): void
```

## OptionsApiRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an `OPTIONS` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\OptionsApiRoute;

#[OptionsApiRoute('example', '/example')]
public function example(): void
```

## OptionsMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `OPTIONS` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\OptionsMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[OptionsMethod]
public function example(): void
```

## OptionsRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an `OPTIONS` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\OptionsRoute;

#[OptionsRoute('example', '/example')]
public function example(): void
```

## PatchApiRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PATCH` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PatchApiRoute;

#[PatchApiRoute('example', '/example')]
public function example(): void
```

## PatchMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `PATCH` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PatchMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PatchMethod]
public function example(): void
```

## PatchRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PATCH` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PatchRoute;

#[PatchRoute('example', '/example')]
public function example(): void
```

## PathPostfix

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets a postfix for an operation path.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: Think twice before using this annotation in your project. It may lead to confusion when a QA engineer, front-end developer, or another team member asks about an operation. Instead of easily searching for the controller, you might end up unraveling a web of annotations. **Overusing this annotation can potentially cause more harm than good**.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\PathPostfix;

#[PathPostfix('.json')]
final class ExampleController
{
    #[GetApiRoute('api.operations.example', '/api/operations/example')]
    public function example(): void
    {
    }
}
```

## PathPrefix

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets a prefix for an operation path.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: Think twice before using this annotation in your project. It may lead to confusion when a QA engineer, front-end developer, or another team member asks about an operation. Instead of easily searching for the controller, you might end up unraveling a web of annotations. **Overusing this annotation can potentially cause more harm than good**.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\PathPrefix;

#[PathPrefix('/api/operations')]
final class ExampleController
{
    #[GetApiRoute('api.operations.example', '/example')]
    public function example(): void
    {
    }
}
```

## Pattern

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets a pattern for a route variable.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: You can also specify the pattern directly in the route – `{id<\d+>}`.

> 💡 **Tip**: Pay attention to the `\Sunrise\Http\Router\Dictionary\VariablePattern` dictionary.

> ❗ **Important**: Specify not a Regular Expression, but a subpattern, i.e., an expression without delimiters and modifiers.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Pattern;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.user.read', '/api/user/{id}')]
#[Pattern('id', '\d+')]
public function read(#[RequestVariable] int $id): void
```

## PostApiRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `POST` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PostApiRoute;

#[PostApiRoute('example', '/example')]
public function example(): void
```

## PostMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `POST` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PostMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PostMethod]
public function example(): void
```

## PostRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `POST` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PostRoute;

#[PostRoute('example', '/example')]
public function example(): void
```

## Priority

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the priority for a route.

This rare annotation is used to assign a priority to a route. Avoid using it within a single project. It is intended for extending the router's functionality, such as when a provider supplies routes and you need to override them in your project.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: This annotation allows you to override Swagger and OpenAPI document routes.

> ❗ **Important**: Do not overuse this annotation.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Priority;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Priority(1)]
public function example(): void
```

## Produces

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

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

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PURGE` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PurgeApiRoute;

#[PurgeApiRoute('example', '/example')]
public function example(): void
```

## PurgeMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `PURGE` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PurgeMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PurgeMethod]
public function example(): void
```

## PurgeRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PURGE` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PurgeRoute;

#[PurgeRoute('example', '/example')]
public function example(): void
```

## PutApiRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PUT` API operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PutApiRoute;

#[PutApiRoute('example', '/example')]
public function example(): void
```

## PutMethod

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the `PUT` HTTP method for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PutMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PutMethod]
public function example(): void
```

## PutRoute

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PUT` operation.

> 💡 **Tip**: The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PutRoute;

#[PutRoute('example', '/example')]
public function example(): void
```

## RequestBody

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Used to bind a request body to an operation parameter.

> 💡 **Tip**: If you need to override the [default error status code](/docs/reference/parameters.md#routerrequest_body_parameter_resolverdefault_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> 💡 **Tip**: If you need to override the [default error message](/docs/reference/parameters.md#routerrequest_body_parameter_resolverdefault_error_message), set it in the `errorMessage` parameter of the annotation.

> 💡 **Tip**: If you need to pass [additional context](/docs/reference/parameters.md#routerrequest_body_parameter_resolverhydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> 💡 **Tip:** If you need to change the [default validator activity](/docs/reference/parameters.md#routerrequest_body_parameter_resolverdefault_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

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

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Used to bind a request cookie to an operation parameter.

> 💡 **Tip**: If you need to override the [default error status code](/docs/reference/parameters.md#routerrequest_cookie_parameter_resolverdefault_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> 💡 **Tip**: If you need to override the [default error message](/docs/reference/parameters.md#routerrequest_cookie_parameter_resolverdefault_error_message), set it in the `errorMessage` parameter of the annotation.

> 💡 **Tip**: If you need to pass [additional context](/docs/reference/parameters.md#routerrequest_cookie_parameter_resolverhydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> 💡 **Tip:** If you need to change the [default validator activity](/docs/reference/parameters.md#routerrequest_cookie_parameter_resolverdefault_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestCookie;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
public function example(#[RequestCookie('foo')] string $foo): void
```

## RequestHeader

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Used to bind a request header to an operation parameter.

> 💡 **Tip**: If you need to override the [default error status code](/docs/reference/parameters.md#routerrequest_header_parameter_resolverdefault_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> 💡 **Tip**: If you need to override the [default error message](/docs/reference/parameters.md#routerrequest_header_parameter_resolverdefault_error_message), set it in the `errorMessage` parameter of the annotation.

> 💡 **Tip**: If you need to pass [additional context](/docs/reference/parameters.md#routerrequest_header_parameter_resolverhydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> 💡 **Tip:** If you need to change the [default validator activity](/docs/reference/parameters.md#routerrequest_header_parameter_resolverdefault_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestHeader;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
public function example(#[RequestHeader('X-Foo')] string $foo): void
```

## RequestQuery

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Used to bind a request query to an operation parameter.

> 💡 **Tip**: If you need to override the [default error status code](/docs/reference/parameters.md#routerrequest_query_parameter_resolverdefault_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> 💡 **Tip**: If you need to override the [default error message](/docs/reference/parameters.md#routerrequest_query_parameter_resolverdefault_error_message), set it in the `errorMessage` parameter of the annotation.

> 💡 **Tip**: If you need to pass [additional context](/docs/reference/parameters.md#routerrequest_query_parameter_resolverhydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> 💡 **Tip:** If you need to change the [default validator activity](/docs/reference/parameters.md#routerrequest_query_parameter_resolverdefault_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

```php
use App\Dto\User\UserSearchRequest;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestQuery;

#[GetApiRoute('api.users.list', '/api/users')]
public function list(#[RequestQuery] UserSearchRequest $userSearchRequest): void
```

## RequestVariable

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Used to bind a route variable to an operation parameter.

> 💡 **Tip**: If you need to override the [default error status code](/docs/reference/parameters.md#routerrequest_variable_parameter_resolverdefault_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> 💡 **Tip**: If you need to override the [default error message](/docs/reference/parameters.md#routerrequest_variable_parameter_resolverdefault_error_message), set it in the `errorMessage` parameter of the annotation.

> 💡 **Tip**: If you need to pass [additional context](/docs/reference/parameters.md#routerrequest_variable_parameter_resolverhydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> 💡 **Tip:** If you need to change the [default validator activity](/docs/reference/parameters.md#routerrequest_variable_parameter_resolverdefault_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

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

## RequestedEntity

Part of the package: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

Used to bind a requested entity to an operation's parameter.

By default, it expects a variable in the route with the same name as the entity's identifier field. In other words, if the entity's identifier field is named `id`, then the variable in the route should be named `{id}` as well.

> 💡 **Tip**: To change the name of the field used to find the entity, set it in the `field` parameter of the annotation. However, keep in mind that a route variable with the same name will also be expected.

> 💡 **Tip**: To change the name of the variable whose value will be used to find the entity, set it in the `variable` parameter of the annotation.

> 💡 **Tip**: To pass additional search criteria, set them in the `criteria` parameter of the annotation.

> 💡 **Tip**: To change the [default entity manager](/docs/reference/parameters.md#routerrequested_entity_parameter_resolverdefault_entity_manager_name), set the name of the required entity manager in the `em` parameter of the annotation.

```php
use App\Dictionary\MediaType;
use App\Entity\User;
use App\View\User\UserView;
use Sunrise\Bridge\Doctrine\Integration\Router\Annotation\RequestedEntity;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;

#[GetApiRoute('api.users.read', '/api/users/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestedEntity] User $user): UserView
```

## ResponseHeader

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets a response header.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\ResponseHeader;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[ResponseHeader('X-Foo', 'foo')]
public function example(): void
```

## ResponseStatus

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets a response status.

> 💡 **Tip**: Pay attention to the `ResponseStatus::STATUS_*` constants.

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

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an operation.

> 💡 **Tip**: You may want to use one of the following annotations: [DeleteRoute](#deleteroute), [GetRoute](#getroute), [HeadRoute](#headroute), [OptionsRoute](#optionsroute), [PatchRoute](#patchroute), [PatchRoute](#patchroute), [PostRoute](#postroute), [PurgeRoute](#purgeroute), [PutRoute](#putroute).

> 💡 **Tip**: The following annotations may be useful for you: [Method](#method), [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

> 💡 **Tip**: Pay attention to the `Route::METHOD_*` annotation constants.

```php
use Sunrise\Http\Router\Annotation\Route;

#[Route('example', '/example', methods: ['GET'])]
public function example(): void
```

## Summary

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Sets the summary for an operation

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

> 💡 **Tip**: Use multiple annotations if the summary is too long, and the router will combine them into one.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Summary;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Summary('Lorem Ipsum...')]
public function example(): void
```

## Tag

Part of the package: [sunrise/http-router](/docs/packages/sunrise/http-router/)

Adds tag(s) for an operation.

> 💡 **Tip**: This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Tag;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Tag('foo')]
public function example(): void
```
