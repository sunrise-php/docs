# Parameter Reference

## app.commands

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `list<\Symfony\Component\Console\Command\Command>`

## app.env

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.input_timestamp_format

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.name

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.output_timestamp_format

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.root

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.timezone_identifier

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.version

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## coder.codecs

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `list<\Sunrise\Coder\CodecInterface>`

## coder.context

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `array<string, mixed>`

## coder.json_codec.context

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `array<string, mixed>`

## coder.url_encoded_codec.context

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `array<string, mixed>`

## curl.multi_select_sleep_duration

**Part of the package**: [sunrise/http-curl-client](/docs/packages/sunrise/http-client-curl/)

**Recommended location**: `config/definitions/curl.php`

**Expected data type**: `int|null`

## curl.multi_select_timeout

**Part of the package**: [sunrise/http-curl-client](/docs/packages/sunrise/http-client-curl/)

**Recommended location**: `config/definitions/curl.php`

**Expected data type**: `float|null`

## curl.options

**Part of the package**: [sunrise/http-curl-client](/docs/packages/sunrise/http-client-curl/)

**Recommended location**: `config/definitions/curl.php`

**Expected data type**: `array<int, mixed>`

## doctrine.entity_manager_parameters.*.default_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.*.entity_directories

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<string>`

## doctrine.entity_manager_parameters.*.logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.entity_manager_parameters.*.naming_strategy

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Mapping\NamingStrategy`

## doctrine.entity_manager_parameters.*.proxy_autogenerate

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Proxy\ProxyFactory::AUTOGENERATE_*`

## doctrine.entity_manager_parameters.*.proxy_directory

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.*.proxy_namespace

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.default_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.default.dsn

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.entity_directories

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<string>`

## doctrine.entity_manager_parameters.default.logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.entity_manager_parameters.default.metadata_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.default.name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface`

## doctrine.entity_manager_parameters.default.naming_strategy

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Mapping\NamingStrategy`

## doctrine.entity_manager_parameters.default.proxy_autogenerate

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Proxy\ProxyFactory::AUTOGENERATE_*`

## doctrine.entity_manager_parameters.default.proxy_directory

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.proxy_namespace

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.query_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.default.result_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters_list

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Sunrise\Bridge\Doctrine\EntityManagerParametersInterface>`

## doctrine.entity_manager_registry.logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.system_temporary_directory

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## hydrator.context

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `array<string, mixed>`

## hydrator.context.timestamp_format

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `string`

## hydrator.context.timezone_identifier

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `string`

## hydrator.map_entity_type_converter.default_entity_manager_name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface|null`

## hydrator.type_converters

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `list<\Sunrise\Hydrator\TypeConverterInterface>`

## logger.handlers

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `list<\Monolog\Handler\HandlerInterface>`

## logger.name

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `string`

## logger.processors

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `list<\Monolog\Processor\ProcessorInterface>`

## logger.stream_handler.logging_level

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `string`

## logger.stream_handler.stream_uri

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `string`

## logger.timezone

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `\DateTimeZone`

## recaptcha.verification.codec_context

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `array<string, mixed>`

## recaptcha.verification.hydrator_context

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `array<string, mixed>`

## recaptcha.verification.private_key

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string`

## router.default_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.descriptor_loader.cache

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Psr\SimpleCache\CacheInterface|null`

## router.descriptor_loader.resources

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<string>`

## router.encodable_response_resolver.codec_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.encodable_response_resolver.default_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.error_handling_middleware.codec_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.error_handling_middleware.default_language

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Http\Router\LanguageInterface`

## router.error_handling_middleware.default_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.error_handling_middleware.fatal_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.error_handling_middleware.fatal_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.error_handling_middleware.produced_languages

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\LanguageInterface>`

## router.error_handling_middleware.produced_media_types

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Coder\MediaTypeInterface>`

## router.event_dispatcher

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Psr\EventDispatcher\EventDispatcherInterface|null`

## router.loaders

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\Loader\LoaderInterface>`

## router.middlewares

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<mixed>`

## router.openapi.default_response_description

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.openapi.default_timestamp_format

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.openapi.document_encoding_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.openapi.document_filename

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.openapi.document_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.openapi.initial_document

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<array-key, mixed>`

## router.openapi.initial_document.info

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<array-key, mixed>`

## router.openapi.initial_operation

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<array-key, mixed>`

## router.openapi.operation_enrichers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\OpenApi\OpenApiOperationEnricherInterface>`

## router.openapi.php_type_schema_resolvers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\OpenApi\OpenApiPhpTypeSchemaResolverInterface>`

## router.parameter_resolvers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\ParameterResolverInterface>`

## router.payload_decoding_middleware.codec_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.recaptcha_challenge_middleware.challenge_failed_message

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string|null`

## router.recaptcha_challenge_middleware.challenge_failed_status_code

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `int|null`

## router.recaptcha_challenge_middleware.empty_token_message

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string|null`

## router.recaptcha_challenge_middleware.empty_token_status_code

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `int|null`

## router.recaptcha_challenge_middleware.token_header_name

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string|null`

## router.request_body_parameter_resolver.default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_body_parameter_resolver.default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_body_parameter_resolver.default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_body_parameter_resolver.hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_cookie_parameter_resolver.default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_cookie_parameter_resolver.default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_cookie_parameter_resolver.default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_cookie_parameter_resolver.hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_header_parameter_resolver.default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_header_parameter_resolver.default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_header_parameter_resolver.default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_header_parameter_resolver.hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_query_parameter_resolver.default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_query_parameter_resolver.default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_query_parameter_resolver.default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_query_parameter_resolver.hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_termination_middleware.clearable_entity_manager_names

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Sunrise\Bridge\Doctrine\EntityManagerNameInterface>`

## router.request_termination_middleware.flushable_entity_manager_names

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Sunrise\Bridge\Doctrine\EntityManagerNameInterface>`

## router.request_variable_parameter_resolver.default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_variable_parameter_resolver.default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_variable_parameter_resolver.default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_variable_parameter_resolver.hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.requested_entity_parameter_resolver.default_entity_manager_name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface|null`

## router.response_resolvers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\ResponseResolverInterface>`

## router.route_middlewares

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<mixed>`

## router.string_trimming_middleware.trimmer

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `(\Closure(string):string)|null`

## router.swagger.css_urls

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<string>`

## router.swagger.js_urls

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<string>`

## router.swagger.openapi_uri

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.swagger.template_filename

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.swagger.template_variables

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## translator.translators

**Part of the package**: [sunrise/translator](/docs/packages/sunrise/translator/)

**Recommended location**: `config/definitions/translator.php`

**Expected data type**: `list<\Sunrise\Translator\TranslatorInterface>`

## validator.unique_entity.default_entity_manager_name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface|null`

## validator.unique_entity.logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`
