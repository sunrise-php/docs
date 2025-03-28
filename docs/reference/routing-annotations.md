# Routing Annotation Reference :id=top

## ApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> You may want to use one of the following annotations: [DeleteApiRoute](#deleteapiroute), [GetApiRoute](#getapiroute), [HeadApiRoute](#headapiroute), [OptionsApiRoute](#optionsapiroute), [PatchApiRoute](#patchapiroute), [PatchApiRoute](#patchapiroute), [PostApiRoute](#postapiroute), [PurgeApiRoute](#purgeapiroute), [PutApiRoute](#putapiroute).

> The following annotations may be useful for you: [Method](#method), [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

> Pay attention to the `ApiRoute::METHOD_*` annotation constants.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;

#[ApiRoute('api.operations.example', '/api/operations/example', 'GET')]
public function example(): void
```

## Constraint

Sets constraints on action parameters, for example, they can be validated using Symfony Validator Constraints.

> This annotation works out-of-the-box with the following annotations: [RequestCookie](#RequestCookie), [RequestHeader](#RequestHeader), [RequestVariable](#RequestVariable).

> Learn how to integrate the Validator into the system. See the [Validator Integration](/docs/cookbook/validator-integration.md) for more details.

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

Sets a media type(s) consumed by an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use App\Dictionary\MediaType;
use App\Dto\Post\PostCreateRequest;
use Sunrise\Http\Router\Annotation\Consumes;
use Sunrise\Http\Router\Annotation\PostApiRoute;
use Sunrise\Http\Router\Annotation\RequestBody;

#[PostApiRoute('api.posts.create', '/api/posts')]
#[Consumes(MediaType::JSON)]
public function create(
    #[RequestBody] PostCreateRequest $postCreateRequest,
): void
```

## DefaultAttribute

Sets a default value for a request attribute.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\DefaultAttribute;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.list', '/api/posts(/{language})')]
#[DefaultAttribute('language', 'en')]
public function list(
    #[RequestVariable] string $language,
): void
```

## DeleteApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `DELETE` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\DeleteApiRoute;

#[DeleteApiRoute('api.operations.example', '/api/operations/example')]
public function example(): void
```

## DeleteMethod

Sets the `DELETE` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\DeleteMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[DeleteMethod]
public function example(): void
```

## DeleteRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `DELETE` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\DeleteRoute;

#[DeleteRoute('example', '/example')]
public function example(): void
```

## Deprecated

Marks an operation as deprecated.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\Deprecated;
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Deprecated]
public function example(): void
```

## Description

Sets a description for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> Use multiple annotations if the description is too long, and the router will combine them into one.

```php
use Sunrise\Http\Router\Annotation\Description;
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Description('Lorem ipsum dolor sit amet...')]
public function example(): void
```

## EncodableResponse

Specifies to encode views returned directly from an action.

> The following annotations may be useful for you: [ResponseStatus](#responsestatus).

> If you need to override the [default media type](/docs/reference/app-parameters.md#router_encodable_response_resolver_default_media_type), set it using the `defaultMediaType` parameter of the annotation.

> If you need to pass [additional operational context](/docs/reference/app-parameters.md#router_encodable_response_resolver_codec_context) to the [encoder](/docs/packages/sunrise/coder/), set it through the `codecContext` parameter of the annotation.

```php
use App\Dictionary\MediaType;
use App\View\Post\PostView;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.read', '/api/posts/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestVariable] int $id): PostView
```

## GetApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `GET` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
public function example(): void
```

## GetMethod

Sets the `GET` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\GetMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[GetMethod]
public function example(): void
```

## GetRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `GET` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\GetRoute;

#[GetRoute('example', '/example')]
public function example(): void
```

## HeadApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `HEAD` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\HeadApiRoute;

#[HeadApiRoute('example', '/example')]
public function example(): void
```

## HeadMethod

Sets the `HEAD` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\HeadMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[HeadMethod]
public function example(): void
```

## HeadRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `HEAD` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\HeadRoute;

#[HeadRoute('example', '/example')]
public function example(): void
```

## Method

Sets a HTTP method(s) for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> Pay attention to the `Method::METHOD_*` constants.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\Method;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[Method('GET')]
public function example(): void
```

## Middleware

Sets middleware(s) for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> A reference to middleware can be an [FQN class name](#middleware-in-the-form-of-an-fqn-class-name) or a [callable notation](#middleware-in-the-form-of-a-callable-notation).

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

> Note that the middleware can be part of the controller.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Middleware;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Middleware([self::class, 'middleware'])]
public function example(): void
```

## NamePrefix

Sets a prefix for an operation name.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> Think twice before using this annotation in your project. It may lead to confusion when a QA engineer, front-end developer, or another team member asks about an operation. Instead of easily searching for the controller, you might end up unraveling a web of annotations. **Overusing this annotation can potentially cause more harm than good**.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\NamePrefix;

#[NamePrefix('api.operations.')]
final readonly class ExampleController
{
    #[GetApiRoute('example', '/api/operations/example')]
    public function example(): void
    {
    }
}
```

## Operation

Allows you to manually document an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> If you need to set a global rule, it's better to use the [router.openapi.initial_document](/docs/reference/app-parameters.md#router_openapi_initial_document) parameter.

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

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an `OPTIONS` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\OptionsApiRoute;

#[OptionsApiRoute('example', '/example')]
public function example(): void
```

## OptionsMethod

Sets the `OPTIONS` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\OptionsMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[OptionsMethod]
public function example(): void
```

## OptionsRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an `OPTIONS` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\OptionsRoute;

#[OptionsRoute('example', '/example')]
public function example(): void
```

## PatchApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PATCH` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PatchApiRoute;

#[PatchApiRoute('example', '/example')]
public function example(): void
```

## PatchMethod

Sets the `PATCH` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PatchMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PatchMethod]
public function example(): void
```

## PatchRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PATCH` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PatchRoute;

#[PatchRoute('example', '/example')]
public function example(): void
```

## PathPostfix

Sets a postfix for an operation path.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> Think twice before using this annotation in your project. It may lead to confusion when a QA engineer, front-end developer, or another team member asks about an operation. Instead of easily searching for the controller, you might end up unraveling a web of annotations. **Overusing this annotation can potentially cause more harm than good**.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\PathPostfix;

#[PathPostfix('.json')]
final readonly class ExampleController
{
    #[GetApiRoute('api.operations.example', '/api/operations/example')]
    public function example(): void
    {
    }
}
```

## PathPrefix

Sets a prefix for an operation path.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> Think twice before using this annotation in your project. It may lead to confusion when a QA engineer, front-end developer, or another team member asks about an operation. Instead of easily searching for the controller, you might end up unraveling a web of annotations. **Overusing this annotation can potentially cause more harm than good**.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\PathPrefix;

#[PathPrefix('/api/operations')]
final readonly class ExampleController
{
    #[GetApiRoute('api.operations.example', '/example')]
    public function example(): void
    {
    }
}
```

## Pattern

Sets a pattern for a route variable.

**Expects not a regex, but a subpattern, i.e., an expression without delimiters and modifiers.**

> Note the [alternative way](/docs/reference/routing-syntax.md#variable-patterns) of defining the pattern.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> Pay attention to the `\Sunrise\Http\Router\Dictionary\VariablePattern` dictionary.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Pattern;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.read', '/api/posts/{id}')]
#[Pattern('id', '\d+')]
public function read(#[RequestVariable] int $id): void
```

## PostApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `POST` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PostApiRoute;

#[PostApiRoute('example', '/example')]
public function example(): void
```

## PostMethod

Sets the `POST` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PostMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PostMethod]
public function example(): void
```

## PostRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `POST` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PostRoute;

#[PostRoute('example', '/example')]
public function example(): void
```

## Priority

Sets a priority for a route.

This rare annotation is used to assign a priority to a route. Avoid using it within a single project. It is intended for extending the router's functionality, such as when a provider supplies routes and you need to override them in your project.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> This annotation allows you to override Swagger and OpenAPI document routes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Priority;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Priority(1)]
public function example(): void
```

## Produces

Sets a media type(s) produced by an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use App\Dictionary\MediaType;
use App\View\Post\PostView;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.read', '/api/posts/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestVariable] int $id): PostView
```

## PurgeApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PURGE` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PurgeApiRoute;

#[PurgeApiRoute('example', '/example')]
public function example(): void
```

## PurgeMethod

Sets the `PURGE` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PurgeMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PurgeMethod]
public function example(): void
```

## PurgeRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PURGE` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PurgeRoute;

#[PurgeRoute('example', '/example')]
public function example(): void
```

## PutApiRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PUT` API operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PutApiRoute;

#[PutApiRoute('example', '/example')]
public function example(): void
```

## PutMethod

Sets the `PUT` HTTP method for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\ApiRoute;
use Sunrise\Http\Router\Annotation\PutMethod;

#[ApiRoute('api.operations.example', '/api/operations/example')]
#[PutMethod]
public function example(): void
```

## PutRoute

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as a `PUT` operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> The following annotations may be useful for you: [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

```php
use Sunrise\Http\Router\Annotation\PutRoute;

#[PutRoute('example', '/example')]
public function example(): void
```

## RequestBody

Used to bind a request body to an action parameter.

> If you need to override the [default error status code](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_default_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> If you need to override the [default error message](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_default_error_message), set it in the `errorMessage` parameter of the annotation.

> If you need to pass [additional operational context](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_hydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> If you need to change the [default validator activity](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_default_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

> We recommend reviewing the [type conversion system](/docs/reference/type-conversion.md) to better understand the binding process.

> Learn how to integrate the Validator into the system. See the [Validator Integration](/docs/cookbook/validator-integration.md) for more details.

```php
use App\Dictionary\MediaType;
use App\Dto\Post\PostCreateRequest;
use Sunrise\Http\Router\Annotation\Consumes;
use Sunrise\Http\Router\Annotation\PostApiRoute;
use Sunrise\Http\Router\Annotation\RequestBody;

#[PostApiRoute('api.posts.create', '/api/posts')]
#[Consumes(MediaType::JSON)]
public function create(
    #[RequestBody] PostCreateRequest $postCreateRequest,
): void
```

## RequestCookie

Used to bind a request cookie to an action parameter.

> If you need to override the [default error status code](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_default_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> If you need to override the [default error message](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_default_error_message), set it in the `errorMessage` parameter of the annotation.

> If you need to pass [additional operational context](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_hydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> If you need to change the [default validator activity](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_default_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

> If the cookie is optional, simply assign a default value to the parameter, for example, `null`.

> We recommend reviewing the [type conversion system](/docs/reference/type-conversion.md) to better understand the binding process.

> Learn how to integrate the Validator into the system. See the [Validator Integration](/docs/cookbook/validator-integration.md) for more details.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestCookie;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
public function example(#[RequestCookie('foo')] string $foo): void
```

## RequestHeader

Used to bind a request header to an action parameter.

> If you need to override the [default error status code](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_default_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> If you need to override the [default error message](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_default_error_message), set it in the `errorMessage` parameter of the annotation.

> If you need to pass [additional operational context](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_hydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> If you need to change the [default validator activity](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_default_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

> If the header is optional, simply assign a default value to the parameter, for example, `null`.

> We recommend reviewing the [type conversion system](/docs/reference/type-conversion.md) to better understand the binding process.

> Learn how to integrate the Validator into the system. See the [Validator Integration](/docs/cookbook/validator-integration.md) for more details.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestHeader;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
public function example(#[RequestHeader('X-Foo')] string $foo): void
```

## RequestQuery

Used to bind a request query to an action parameter.

> If you need to override the [default error status code](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_default_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> If you need to override the [default error message](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_default_error_message), set it in the `errorMessage` parameter of the annotation.

> If you need to pass [additional operational context](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_hydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> If you need to change the [default validator activity](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_default_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

> We recommend reviewing the [type conversion system](/docs/reference/type-conversion.md) to better understand the binding process.

> Learn how to integrate the Validator into the system. See the [Validator Integration](/docs/cookbook/validator-integration.md) for more details.

```php
use App\Dto\Post\PostSearchRequest;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\RequestQuery;

#[GetApiRoute('api.posts.list', '/api/posts')]
public function list(#[RequestQuery] PostSearchRequest $postSearchRequest): void
```

## RequestVariable

Used to bind a route variable to an action parameter.

> By default, the route variable name can be omitted, as the action parameter name will be used. If they don't match, you can specify the route variable name using the `name` parameter of the annotation.

> If you need to override the [default error status code](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_default_error_status_code), set it in the `errorStatusCode` parameter of the annotation.

> If you need to override the [default error message](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_default_error_message), set it in the `errorMessage` parameter of the annotation.

> If you need to pass [additional operational context](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_hydrator_context) to the [hydrator](/docs/packages/sunrise/hydrator/), set it in the `hydratorContext` parameter of the annotation.

> If you need to change the [default validator activity](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_default_validation_enabled), set it in the `validationEnabled` parameter of the annotation.

> If the variable is optional, simply assign a default value to the parameter, for example, `null`.

> We recommend reviewing the [type conversion system](/docs/reference/type-conversion.md) to better understand the binding process.

> Learn how to integrate the Validator into the system. See the [Validator Integration](/docs/cookbook/validator-integration.md) for more details.

```php
use App\Dictionary\MediaType;
use App\View\Post\PostView;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;
use Sunrise\Http\Router\Annotation\RequestVariable;

#[GetApiRoute('api.posts.read', '/api/posts/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestVariable] int $id): PostView
```

## RequestedEntity

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

Used to bind a requested entity to an action's parameter.

By default, it expects a variable in the route with the same name as the entity's identifier field. In other words, if the entity's identifier field is named `id`, then the variable in the route should be named `{id}` as well.

> To change the name of the field used to find the entity, set it in the `field` parameter of the annotation. However, keep in mind that a route variable with the same name will also be expected.

> To change the name of the variable whose value will be used to find the entity, set it in the `variable` parameter of the annotation.

> To pass additional search criteria, set them in the `criteria` parameter of the annotation.

> To change the [default entity manager](/docs/reference/app-parameters.md#router_requested_entity_parameter_resolver_default_entity_manager_name), set the name of the required entity manager in the `em` parameter of the annotation.

```php
use App\Dictionary\MediaType;
use App\Entity\Post;
use App\View\Post\PostView;
use Sunrise\Bridge\Doctrine\Integration\Router\Annotation\RequestedEntity;
use Sunrise\Http\Router\Annotation\EncodableResponse;
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Produces;

#[GetApiRoute('api.posts.read', '/api/posts/{id}')]
#[Produces(MediaType::JSON)]
#[EncodableResponse]
public function read(#[RequestedEntity] Post $post): PostView
```

## ResponseHeader

Sets a response header.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\ResponseHeader;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[ResponseHeader('X-Foo', 'foo')]
public function example(): void
```

## ResponseStatus

Sets a response status.

> Pay attention to the `ResponseStatus::STATUS_*` constants.

```php
use App\Dictionary\MediaType;
use App\Dto\Post\PostCreateRequest;
use App\View\Post\PostView;
use Sunrise\Http\Router\Annotation\Consumes;
use Sunrise\Http\Router\Annotation\PostApiRoute;
use Sunrise\Http\Router\Annotation\RequestBody;
use Sunrise\Http\Router\Annotation\ResponseStatus;

#[PostApiRoute('api.posts.create', '/api/posts')]
#[Consumes(MediaType::JSON)]
#[ResponseStatus(201)]
public function create(
    #[RequestBody] PostCreateRequest $postCreateRequest,
): PostView
```

## Route

Marks a [PSR-15 controller](/docs/cookbook/psr-15-controller.md) or action as an operation.

> Refer to the [Routing Syntax Reference](/docs/reference/routing-syntax.md) to understand the route syntax.

> You may want to use one of the following annotations: [DeleteRoute](#deleteroute), [GetRoute](#getroute), [HeadRoute](#headroute), [OptionsRoute](#optionsroute), [PatchRoute](#patchroute), [PatchRoute](#patchroute), [PostRoute](#postroute), [PurgeRoute](#purgeroute), [PutRoute](#putroute).

> The following annotations may be useful for you: [Method](#method), [NamePrefix](#nameprefix), [PathPrefix](#pathprefix).

> Pay attention to the `Route::METHOD_*` annotation constants.

```php
use Sunrise\Http\Router\Annotation\Route;

#[Route('example', '/example', methods: ['GET'])]
public function example(): void
```

## Summary

Sets a summary for an operation

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

> Use multiple annotations if the summary is too long, and the router will combine them into one.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Summary;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Summary('Lorem Ipsum...')]
public function example(): void
```

## Tag

Adds tag(s) for an operation.

> This annotation can be applied not only to an action but also to a class and even to its parent classes.

```php
use Sunrise\Http\Router\Annotation\GetApiRoute;
use Sunrise\Http\Router\Annotation\Tag;

#[GetApiRoute('api.operations.example', '/api/operations/example')]
#[Tag('foo')]
public function example(): void
```
