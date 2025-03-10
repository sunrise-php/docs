# Router Reference :id=top

## Getting the Route

To get the route by name, use the following method:

```php
$route = $router->getRoute('foo');
```

To check the existence of a route by name, use the following method:

```php
if ($router->hasRoute('foo')) {
    // Some code...
}
```

To get the **requested route**, use the following method:

```php
use Sunrise\Http\Router\RouteInterface;

$route = $request->getAttribute(RouteInterface::class);
```

## Route Building

To build the route, i.e., convert its [syntax path](/docs/reference/routing-syntax.md) to a URI path, use the following method:

```php
$path = $router->buildRoute($route);
```

To build a route with variables, use the following method:

```php
// If the route is `/{foo}`, then the expected result is `/bar`.
$path = $router->buildRoute($route, ['foo' => 'bar']);
```

To build the route in strict mode, use the following method:

```php
// If the route is `/{foo<bar>}`, an error will occur
// because `baz` is an unexpected value for the route variable `foo`.
$path = $router->buildRoute($route, ['foo' => 'baz'], true);
```

## Route Running

To run the route, use the following method:

```php
$response = $router->runRoute($route, $request);
```
