# Typed Collection :id=top

A typed collection is essentially the same [collection](/docs/reference/type-conversion.md#collection), but its elements are typed not through the [Subtype](/docs/reference/hydrator-annotations.md#subtype) annotation, but by explicitly specifying the type in its constructor.

To properly type a collection, its constructor must declare a typed [variadic](https://www.php.net/manual/en/functions.arguments.php#functions.variable-arg-list) parameter, and the type of this parameter will be the type of this collection.
The type of this collection can be anything supported by the [type conversion system](/docs/reference/type-conversion.md).

If it is necessary to limit a collection to a maximum number of elements, the [offsetSet](https://www.php.net/manual/en/arrayaccess.offsetset.php) method should throw the [OverflowException](https://www.php.net/manual/en/class.overflowexception.php) when the limit is exceeded.
It is recommended to use limited collections to avoid memory leaks.

```php
/**
 * @extends \ArrayObject<array-key, string>
 */
final class ExampleCollection extends \ArrayObject
{
    public function __construct(string ...$values)
    {
        parent::__construct($values);
    }
}
```
