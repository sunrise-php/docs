# Custom Type Converter

As an example, let's create a type converter for monetary values.
This converter will expect a monetary value as input and return the `\BcMath\Number` as output.

```php
declare(strict_types=1);

namespace App\TypeConverter;

use BcMath\Number;
use Sunrise\Hydrator\Exception\InvalidValueException;
use Sunrise\Hydrator\Type;
use Sunrise\Hydrator\TypeConverterInterface;

final readonly class MonetaryTypeConverter implements TypeConverterInterface
{
    public function castValue($value, Type $type, array $path, array $context): \Generator
    {
        if ($type->getName() !== Number::class) {
            return;
        }

        if (!\is_string($value)) {
            throw InvalidValueException::mustBeString($path, $value);
        }

        $value = \trim($value);
        if ($value === '') {
            // As part of supporting untyped data sources, empty strings should be considered as NULL.
            return $type->allowsNull() ? yield : throw InvalidValueException::mustNotBeEmpty($path, $value);
        }

        try {
            yield new Number($value);
        } catch (\ValueError) {
            throw InvalidValueException::mustBeNumber($path, $value);
        }
    }

    public function getWeight(): int
    {
        return 85;
    }
}
```

Now, let's register this type converter in the system.
Open the `config/definitions/hydrator.php` configuration file and modify it as follows:

```php
declare(strict_types=1);

use App\TypeConverter\MonetaryTypeConverter;

use function DI\add;
use function DI\create;

return [
    'hydrator.type_converters' => add([
        create(MonetaryTypeConverter::class),
    ]),
];
```

Now you can use the new type in the project as follows:

```php
public readonly \BcMath\Number $price
```
