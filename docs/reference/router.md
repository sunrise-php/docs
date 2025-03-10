# Router Reference :id=top

## Route Building

To build the route, i.e., convert its [syntax path](/docs/reference/routing-syntax.md) to a URI path, use the following method:

```php
$path = $router->buildRoute($route);
```

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

## Route Running

To run the route, use the following method:

```php
$response = $router->runRoute($route, $request);
```
