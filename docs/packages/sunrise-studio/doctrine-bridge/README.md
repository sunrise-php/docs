# sunrise-studio/doctrine-bridge :id=top

Doctrine Bridge

![PHP](https://img.shields.io/packagist/dependency-v/sunrise-studio/doctrine-bridge/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-studio-development/doctrine-bridge?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-studio-development/doctrine-bridge?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise-studio/doctrine-bridge?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-studio-development/doctrine-bridge?style=social)

## Installation

```bash
composer require sunrise-studio/doctrine-bridge
```

This package also requires [PSR-6](https://www.php-fig.org/psr/psr-6/) compatible package;
we recommend [symfony/cache](https://packagist.org/packages/symfony/cache).

```bash
composer require symfony/cache
```

## Quick Start

```php

use Doctrine\ORM\Mapping\UnderscoreNamingStrategy;
use Doctrine\ORM\Proxy\ProxyFactory;
use Sunrise\Bridge\Doctrine\Dictionary\EntityManagerName;
use Sunrise\Bridge\Doctrine\EntityManagerFactory;
use Sunrise\Bridge\Doctrine\EntityManagerParameters;
use Sunrise\Bridge\Doctrine\EntityManagerRegistry;
use Symfony\Component\Cache\Adapter\ArrayAdapter;

$entityManagerParameters = new EntityManagerParameters(
    name: EntityManagerName::Default,
    // Store the DSN in an environment variable, e.g., `DATABASE_DSN`.
    dsn: 'pdo-pgsql://user:password@localhost:5432/acme?charset=utf8',
    // Names of directories storing your entities.
    entityDirectories: [__DIR__ . '/src/Entity'],
    proxyDirectory: \sys_get_temp_dir() . '/doctrine-proxies',
    proxyNamespace: 'DoctrineProxies',
    // For production, use `ProxyFactory::AUTOGENERATE_NEVER`,
    // but remember to generate entity proxies before deployment.
    proxyAutogenerate: ProxyFactory::AUTOGENERATE_ALWAYS,
    // For production, use `RedisAdapter`, for example.
    metadataCache: new ArrayAdapter(),
    // For production, use `RedisAdapter`, for example.
    queryCache: new ArrayAdapter(),
    // For production, use `RedisAdapter`, for example.
    resultCache: new ArrayAdapter(),
    namingStrategy: new UnderscoreNamingStrategy(),
    logger: null,
);

$entityManagerRegistry = new EntityManagerRegistry(
    entityManagerFactory: new EntityManagerFactory(),
    entityManagerParametersList: [$entityManagerParameters],
    defaultEntityManagerName: EntityManagerName::Default,
    logger: null,
);

// Default Entity Manager
$entityManager = $entityManagerRegistry->getEntityManager();
```

## What's Next

- Refer to the hydrator annotation [MapEntity](/docs/reference/hydrator-annotations.md#mapentity), which allows binding the requested entity to a class property (typically a DTO).
- Refer to the routing annotation [RequestedEntity](/docs/reference/routing-annotations.md#requestedentity), which allows binding the requested entity to a controller action parameter.
- Refer to the [RequestTerminationMiddleware](/docs/reference/middlewares.md#requestterminationmiddleware) middleware, which commits database changes after each request.
- Refer to the [UniqueEntity](/docs/reference/validator-constraints.md#uniqueentity) constraint, which ensures entity uniqueness.

## Awesome Skeleton

### Integration

```php
$containerBuilder->addDefinitions(
    __DIR__ . '/../vendor/sunrise-studio/doctrine-bridge/resources/definitions/doctrine.php',
    __DIR__ . '/../vendor/sunrise-studio/doctrine-bridge/resources/definitions/integration/hydrator/type_converters/map_entity_type_converter.php',
    __DIR__ . '/../vendor/sunrise-studio/doctrine-bridge/resources/definitions/integration/router/middlewares/request_termination_middleware.php',
    __DIR__ . '/../vendor/sunrise-studio/doctrine-bridge/resources/definitions/integration/router/parameter_resolvers/requested_entity_parameter_resolver.php',
    __DIR__ . '/../vendor/sunrise-studio/doctrine-bridge/resources/definitions/integration/validator/unique_entity_validator.php',
);
```

### Parameters

- [doctrine.entity_manager_parameters.*.default_cache](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_cache)
- [doctrine.entity_manager_parameters.*.entity_directories](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_entity_directories)
- [doctrine.entity_manager_parameters.*.logger](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_logger)
- [doctrine.entity_manager_parameters.*.naming_strategy](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_naming_strategy)
- [doctrine.entity_manager_parameters.*.proxy_autogenerate](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_proxy_autogenerate)
- [doctrine.entity_manager_parameters.*.proxy_directory](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_proxy_directory)
- [doctrine.entity_manager_parameters.*.proxy_namespace](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_proxy_namespace)
- [doctrine.entity_manager_parameters.default.default_cache](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_default_cache)
- [doctrine.entity_manager_parameters.default.dsn](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_dsn)
- [doctrine.entity_manager_parameters.default.entity_directories](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_entity_directories)
- [doctrine.entity_manager_parameters.default.logger](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_logger)
- [doctrine.entity_manager_parameters.default.metadata_cache](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_metadata_cache)
- [doctrine.entity_manager_parameters.default.name](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_name)
- [doctrine.entity_manager_parameters.default.naming_strategy](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_naming_strategy)
- [doctrine.entity_manager_parameters.default.proxy_autogenerate](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_proxy_autogenerate)
- [doctrine.entity_manager_parameters.default.proxy_directory](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_proxy_directory)
- [doctrine.entity_manager_parameters.default.proxy_namespace](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_proxy_namespace)
- [doctrine.entity_manager_parameters.default.query_cache](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_query_cache)
- [doctrine.entity_manager_parameters.default.result_cache](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_default_result_cache)
- [doctrine.entity_manager_parameters_list](/docs/reference/app-parameters.md#doctrine_entity_manager_parameters_list)
- [doctrine.entity_manager_registry.logger](/docs/reference/app-parameters.md#doctrine_entity_manager_registry_logger)
- [doctrine.logger](/docs/reference/app-parameters.md#doctrine_logger)
- [doctrine.system_temporary_directory](/docs/reference/app-parameters.md#doctrine_system_temporary_directory)

#### MapEntityTypeConverter Parameters

- [hydrator.map_entity_type_converter.default_entity_manager_name](/docs/reference/app-parameters.md#hydrator_map_entity_type_converter_default_entity_manager_name)

#### RequestTerminationMiddleware Parameters

- [router.request_termination_middleware.flushable_entity_manager_names](/docs/reference/app-parameters.md#router_request_termination_middleware_flushable_entity_manager_names)
- [router.request_termination_middleware.clearable_entity_manager_names](/docs/reference/app-parameters.md#router_request_termination_middleware_clearable_entity_manager_names)

#### RequestedEntityParameterResolver Parameters

- [router.requested_entity_parameter_resolver.default_entity_manager_name](/docs/reference/app-parameters.md#router_requested_entity_parameter_resolver_default_entity_manager_name)

#### UniqueEntityValidator Parameters

- [validator.unique_entity.default_entity_manager_name](/docs/reference/app-parameters.md#validator_unique_entity_default_entity_manager_name)
- [validator.unique_entity.logger](/docs/reference/app-parameters.md#validator_unique_entity_logger)
