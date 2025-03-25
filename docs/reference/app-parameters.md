# Application Parameter Reference :id=top

## app.commands :id=app_commands

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `list<\Symfony\Component\Console\Command\Command>`

## app.env :id=app_env

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.input_timestamp_format :id=app_input_timestamp_format

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.name :id=app_name

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.output_timestamp_format :id=app_output_timestamp_format

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.root :id=app_root

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.timezone_identifier :id=app_timezone_identifier

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## app.version :id=app_version

**Recommended location**: `config/definitions/app.php`

**Expected data type**: `string`

## coder.codecs :id=coder_codecs

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `list<\Sunrise\Coder\CodecInterface>`

## coder.context :id=coder_context

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `array<string, mixed>`

## coder.json_codec.context :id=coder_json_codec_context

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `array<string, mixed>`

## coder.url_encoded_codec.context :id=coder_url_encoded_codec_context

**Part of the package**: [sunrise/coder](/docs/packages/sunrise/coder/)

**Recommended location**: `config/definitions/coder.php`

**Expected data type**: `array<string, mixed>`

## curl.multi_select_sleep_duration :id=curl_multi_select_sleep_duration

**Part of the package**: [sunrise/http-curl-client](/docs/packages/sunrise/http-client-curl/)

**Recommended location**: `config/definitions/curl.php`

**Expected data type**: `int|null`

## curl.multi_select_timeout :id=curl_multi_select_timeout

**Part of the package**: [sunrise/http-curl-client](/docs/packages/sunrise/http-client-curl/)

**Recommended location**: `config/definitions/curl.php`

**Expected data type**: `float|null`

## curl.options :id=curl_options

**Part of the package**: [sunrise/http-curl-client](/docs/packages/sunrise/http-client-curl/)

**Recommended location**: `config/definitions/curl.php`

**Expected data type**: `array<int, mixed>`

## doctrine.entity_manager_parameters.*.default_cache :id=doctrine_entity_manager_parameters_default_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.*.entity_directories :id=doctrine_entity_manager_parameters_entity_directories

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<string>`

## doctrine.entity_manager_parameters.*.event_listeners :id=doctrine_entity_manager_parameters_event_listeners

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `array<string, object>`

## doctrine.entity_manager_parameters.*.logger :id=doctrine_entity_manager_parameters_logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.entity_manager_parameters.*.middlewares :id=doctrine_entity_manager_parameters_middlewares

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Doctrine\DBAL\Driver\Middleware>`

## doctrine.entity_manager_parameters.*.naming_strategy :id=doctrine_entity_manager_parameters_naming_strategy

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Mapping\NamingStrategy`

## doctrine.entity_manager_parameters.*.proxy_autogenerate :id=doctrine_entity_manager_parameters_proxy_autogenerate

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Proxy\ProxyFactory::AUTOGENERATE_*`

## doctrine.entity_manager_parameters.*.proxy_directory :id=doctrine_entity_manager_parameters_proxy_directory

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.*.proxy_namespace :id=doctrine_entity_manager_parameters_proxy_namespace

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.default_cache :id=doctrine_entity_manager_parameters_default_default_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.default.dsn :id=doctrine_entity_manager_parameters_default_dsn

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.entity_directories :id=doctrine_entity_manager_parameters_default_entity_directories

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<string>`

## doctrine.entity_manager_parameters.default.event_listeners :id=doctrine_entity_manager_parameters_default_event_listeners

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `array<string, object>`

## doctrine.entity_manager_parameters.default.logger :id=doctrine_entity_manager_parameters_default_logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.entity_manager_parameters.default.middlewares :id=doctrine_entity_manager_parameters_default_middlewares

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Doctrine\DBAL\Driver\Middleware>`

## doctrine.entity_manager_parameters.default.metadata_cache :id=doctrine_entity_manager_parameters_default_metadata_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.default.name :id=doctrine_entity_manager_parameters_default_name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface`

## doctrine.entity_manager_parameters.default.naming_strategy :id=doctrine_entity_manager_parameters_default_naming_strategy

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Mapping\NamingStrategy`

## doctrine.entity_manager_parameters.default.proxy_autogenerate :id=doctrine_entity_manager_parameters_default_proxy_autogenerate

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Doctrine\ORM\Proxy\ProxyFactory::AUTOGENERATE_*`

## doctrine.entity_manager_parameters.default.proxy_directory :id=doctrine_entity_manager_parameters_default_proxy_directory

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.proxy_namespace :id=doctrine_entity_manager_parameters_default_proxy_namespace

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## doctrine.entity_manager_parameters.default.query_cache :id=doctrine_entity_manager_parameters_default_query_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters.default.result_cache :id=doctrine_entity_manager_parameters_default_result_cache

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Cache\CacheItemPoolInterface`

## doctrine.entity_manager_parameters_list :id=doctrine_entity_manager_parameters_list

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Sunrise\Bridge\Doctrine\EntityManagerParametersInterface>`

## doctrine.entity_manager_registry.logger :id=doctrine_entity_manager_registry_logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.logger :id=doctrine_logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`

## doctrine.system_temporary_directory :id=doctrine_system_temporary_directory

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `string`

## hydrator.context :id=hydrator_context

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `array<string, mixed>`

## hydrator.context.timestamp_format :id=hydrator_context_timestamp_format

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `string`

## hydrator.context.timezone_identifier :id=hydrator_context_timezone_identifier

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `string`

## hydrator.map_entity_type_converter.default_entity_manager_name :id=hydrator_map_entity_type_converter_default_entity_manager_name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface|null`

## hydrator.type_converters :id=hydrator_type_converters

**Part of the package**: [sunrise/hydrator](/docs/packages/sunrise/hydrator/)

**Recommended location**: `config/definitions/hydrator.php`

**Expected data type**: `list<\Sunrise\Hydrator\TypeConverterInterface>`

## logger.handlers :id=logger_handlers

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `list<\Monolog\Handler\HandlerInterface>`

## logger.name :id=logger_name

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `string`

## logger.processors :id=logger_processors

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `list<\Monolog\Processor\ProcessorInterface>`

## logger.stream_handler.logging_level :id=logger_stream_handler_logging_level

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `string`

## logger.stream_handler.stream_uri :id=logger_stream_handler_stream_uri

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `string`

## logger.timezone :id=logger_timezone

**Recommended location**: `config/definitions/logger.php`

**Expected data type**: `\DateTimeZone`

## recaptcha.verification.codec_context :id=recaptcha_verification_codec_context

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `array<string, mixed>`

## recaptcha.verification.hydrator_context :id=recaptcha_verification_hydrator_context

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `array<string, mixed>`

## recaptcha.verification.private_key :id=recaptcha_verification_private_key

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string`

## router.default_media_type :id=router_default_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.descriptor_loader.cache :id=router_descriptor_loader_cache

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Psr\SimpleCache\CacheInterface|null`

## router.descriptor_loader.resources :id=router_descriptor_loader_resources

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<string>`

## router.encodable_response_resolver.codec_context :id=router_encodable_response_resolver_codec_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.encodable_response_resolver.default_media_type :id=router_encodable_response_resolver_default_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.error_handling_middleware.codec_context :id=router_error_handling_middleware_codec_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.error_handling_middleware.default_language :id=router_error_handling_middleware_default_language

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Http\Router\LanguageInterface`

## router.error_handling_middleware.default_media_type :id=router_error_handling_middleware_default_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.error_handling_middleware.fatal_error_message :id=router_error_handling_middleware_fatal_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.error_handling_middleware.fatal_error_status_code :id=router_error_handling_middleware_fatal_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.error_handling_middleware.produced_languages :id=router_error_handling_middleware_produced_languages

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\LanguageInterface>`

## router.error_handling_middleware.produced_media_types :id=router_error_handling_middleware_produced_media_types

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Coder\MediaTypeInterface>`

## router.event_dispatcher :id=router_event_dispatcher

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Psr\EventDispatcher\EventDispatcherInterface|null`

## router.loaders :id=router_loaders

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\Loader\LoaderInterface>`

## router.middlewares :id=router_middlewares

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<mixed>`

## router.openapi.default_response_description :id=router_openapi_default_response_description

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.openapi.default_timestamp_format :id=router_openapi_default_timestamp_format

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.openapi.document_encoding_context :id=router_openapi_document_encoding_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.openapi.document_filename :id=router_openapi_document_filename

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.openapi.document_media_type :id=router_openapi_document_media_type

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `\Sunrise\Coder\MediaTypeInterface`

## router.openapi.initial_document :id=router_openapi_initial_document

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<array-key, mixed>`

## router.openapi.initial_document.info :id=router_openapi_initial_document_info

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<array-key, mixed>`

## router.openapi.initial_operation :id=router_openapi_initial_operation

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<array-key, mixed>`

## router.openapi.operation_enrichers :id=router_openapi_operation_enrichers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\OpenApi\OpenApiOperationEnricherInterface>`

## router.openapi.php_type_schema_resolvers :id=router_openapi_php_type_schema_resolvers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\OpenApi\OpenApiPhpTypeSchemaResolverInterface>`

## router.parameter_resolvers :id=router_parameter_resolvers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\ParameterResolverInterface>`

## router.payload_decoding_middleware.codec_context :id=router_payload_decoding_middleware_codec_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.recaptcha_challenge_middleware.challenge_failed_message :id=router_recaptcha_challenge_middleware_challenge_failed_message

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string|null`

## router.recaptcha_challenge_middleware.challenge_failed_status_code :id=router_recaptcha_challenge_middleware_challenge_failed_status_code

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `int|null`

## router.recaptcha_challenge_middleware.empty_token_message :id=router_recaptcha_challenge_middleware_empty_token_message

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string|null`

## router.recaptcha_challenge_middleware.empty_token_status_code :id=router_recaptcha_challenge_middleware_empty_token_status_code

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `int|null`

## router.recaptcha_challenge_middleware.token_header_name :id=router_recaptcha_challenge_middleware_token_header_name

**Part of the package**: [sunrise/recaptcha](/docs/packages/sunrise/recaptcha/)

**Recommended location**: `config/definitions/recaptcha.php`

**Expected data type**: `string|null`

## router.request_body_parameter_resolver.default_error_message :id=router_request_body_parameter_resolver_default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_body_parameter_resolver.default_error_status_code :id=router_request_body_parameter_resolver_default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_body_parameter_resolver.default_validation_enabled :id=router_request_body_parameter_resolver_default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_body_parameter_resolver.hydrator_context :id=router_request_body_parameter_resolver_hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_cookie_parameter_resolver.default_error_message :id=router_request_cookie_parameter_resolver_default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_cookie_parameter_resolver.default_error_status_code :id=router_request_cookie_parameter_resolver_default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_cookie_parameter_resolver.default_validation_enabled :id=router_request_cookie_parameter_resolver_default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_cookie_parameter_resolver.hydrator_context :id=router_request_cookie_parameter_resolver_hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_header_parameter_resolver.default_error_message :id=router_request_header_parameter_resolver_default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_header_parameter_resolver.default_error_status_code :id=router_request_header_parameter_resolver_default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_header_parameter_resolver.default_validation_enabled :id=router_request_header_parameter_resolver_default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_header_parameter_resolver.hydrator_context :id=router_request_header_parameter_resolver_hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_query_parameter_resolver.default_error_message :id=router_request_query_parameter_resolver_default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_query_parameter_resolver.default_error_status_code :id=router_request_query_parameter_resolver_default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_query_parameter_resolver.default_validation_enabled :id=router_request_query_parameter_resolver_default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_query_parameter_resolver.hydrator_context :id=router_request_query_parameter_resolver_hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.request_termination_middleware.clearable_entity_manager_names :id=router_request_termination_middleware_clearable_entity_manager_names

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Sunrise\Bridge\Doctrine\EntityManagerNameInterface>`

## router.request_termination_middleware.flushable_entity_manager_names :id=router_request_termination_middleware_flushable_entity_manager_names

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `list<\Sunrise\Bridge\Doctrine\EntityManagerNameInterface>`

## router.request_variable_parameter_resolver.default_error_message :id=router_request_variable_parameter_resolver_default_error_message

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string|null`

## router.request_variable_parameter_resolver.default_error_status_code :id=router_request_variable_parameter_resolver_default_error_status_code

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `int|null`

## router.request_variable_parameter_resolver.default_validation_enabled :id=router_request_variable_parameter_resolver_default_validation_enabled

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `bool`

## router.request_variable_parameter_resolver.hydrator_context :id=router_request_variable_parameter_resolver_hydrator_context

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## router.requested_entity_parameter_resolver.default_entity_manager_name :id=router_requested_entity_parameter_resolver_default_entity_manager_name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface|null`

## router.response_resolvers :id=router_response_resolvers

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<\Sunrise\Http\Router\ResponseResolverInterface>`

## router.route_middlewares :id=router_route_middlewares

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<mixed>`

## router.string_trimming_middleware.trimmer :id=router_string_trimming_middleware_trimmer

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `(\Closure(string):string)|null`

## router.swagger.css_urls :id=router_swagger_css_urls

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<string>`

## router.swagger.js_urls :id=router_swagger_js_urls

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `list<string>`

## router.swagger.openapi_uri :id=router_swagger_openapi_uri

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.swagger.template_filename :id=router_swagger_template_filename

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `string`

## router.swagger.template_variables :id=router_swagger_template_variables

**Part of the package**: [sunrise/http-router](/docs/packages/sunrise/http-router/)

**Recommended location**: `config/definitions/router.php`

**Expected data type**: `array<string, mixed>`

## translator.translators :id=translator_translators

**Part of the package**: [sunrise/translator](/docs/packages/sunrise/translator/)

**Recommended location**: `config/definitions/translator.php`

**Expected data type**: `list<\Sunrise\Translator\TranslatorInterface>`

## validator.unique_entity.default_entity_manager_name :id=validator_unique_entity_default_entity_manager_name

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Sunrise\Bridge\Doctrine\EntityManagerNameInterface|null`

## validator.unique_entity.logger :id=validator_unique_entity_logger

**Part of the package**: [sunrise-studio/doctrine-bridge](/docs/packages/sunrise-studio/doctrine-bridge/)

**Recommended location**: `config/definitions/doctrine.php`

**Expected data type**: `\Psr\Log\LoggerInterface|null`
