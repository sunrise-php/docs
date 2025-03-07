# Constraint Reference :id=top

> Learn how to integrate the Validator into the system. See the [Validator Integration](/docs/cookbook/validator-integration.md) for more details.

## RecaptchaChallenge

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

Validates the user's token.

```php
use Sunrise\Recaptcha\Integration\Validator\Constraint\RecaptchaChallenge;

final readonly class SomeDto
{
    public function __construct(
        #[RecaptchaChallenge]
        public readonly $recaptcha,
    ) {
    }
}
```

## UniqueEntity

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

Ensures entity uniqueness based on specified fields.

> If you need to assign an entity manager name different from the [default](/docs/reference/app-parameters.md#validator_unique_entity_default_entity_manager_name), you can do this via the `em` parameter of this annotation.

```php
use Sunrise\Bridge\Doctrine\Integration\Validator\Constraint\UniqueEntity;

#[UniqueEntity(fields: ['slug'])]
class Page
{
}
```
