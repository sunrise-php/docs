# sunrise/http-router :id=top

A powerful solution as the foundation of your project.

![PHP](https://img.shields.io/packagist/dependency-v/sunrise/http-router/php?style=social&logo=php&label=PHP)
![Coverage](https://img.shields.io/scrutinizer/coverage/g/sunrise-php/http-router?style=social)
![Code quality](https://img.shields.io/scrutinizer/quality/g/sunrise-php/http-router?style=social)
![Downloads](https://img.shields.io/packagist/dt/sunrise/http-router?style=social)
![Stars](https://img.shields.io/github/stars/sunrise-php/http-router?style=social)

## Key Features

- Immutable architecture
- Direct injection of DTO objects into controllers
- Sending View objects directly from controllers
- Self-documenting API
- Localization
- Error handling
- High flexibility

## Installation

> We refer to the router as "the foundation of your project" for a reason.
> Setting up the router with all its features can be complex, so we strongly recommend starting with [Awesome Skeleton](/docs/packages/sunrise/awesome-skeleton/), where everything is pre-configured.
> All further documentation assumes that the router is fully integrated into your project.

```bash
composer require sunrise/http-router
```

This package also requires [PSR-7](https://www.php-fig.org/psr/psr-7/) and [PSR-17](https://www.php-fig.org/psr/psr-17/) compatible packages;
we recommend [sunrise/http-message](/docs/packages/sunrise/http-message/).

```bash
composer require sunrise/http-message
```

## Awesome Skeleton

### Integration

Integrated by default.

### Parameters

- [router.default_media_type](/docs/reference/app-parameters.md#router_default_media_type)
- [router.event_dispatcher](/docs/reference/app-parameters.md#router_event_dispatcher)
- [router.loaders](/docs/reference/app-parameters.md#router_loaders)
- [router.middlewares](/docs/reference/app-parameters.md#router_middlewares)
- [router.parameter_resolvers](/docs/reference/app-parameters.md#router_parameter_resolvers)
- [router.response_resolvers](/docs/reference/app-parameters.md#router_response_resolvers)
- [router.route_middlewares](/docs/reference/app-parameters.md#router_route_middlewares)

#### OpenAPI Parameters

- [router.openapi.default_response_description](/docs/reference/app-parameters.md#router_openapi_default_response_description)
- [router.openapi.default_timestamp_format](/docs/reference/app-parameters.md#router_openapi_default_timestamp_format)
- [router.openapi.document_encoding_context](/docs/reference/app-parameters.md#router_openapi_document_encoding_context)
- [router.openapi.document_filename](/docs/reference/app-parameters.md#router_openapi_document_filename)
- [router.openapi.document_media_type](/docs/reference/app-parameters.md#router_openapi_document_media_type)
- [router.openapi.initial_document](/docs/reference/app-parameters.md#router_openapi_initial_document)
- [router.openapi.initial_operation](/docs/reference/app-parameters.md#router_openapi_initial_operation)
- [router.openapi.operation_enrichers](/docs/reference/app-parameters.md#router_openapi_operation_enrichers)
- [router.openapi.php_type_schema_resolvers](/docs/reference/app-parameters.md#router_openapi_php_type_schema_resolvers)

#### Swagger Parameters

- [router.swagger.css_urls](/docs/reference/app-parameters.md#router_swagger_css_urls)
- [router.swagger.js_urls](/docs/reference/app-parameters.md#router_swagger_js_urls)
- [router.swagger.openapi_uri](/docs/reference/app-parameters.md#router_swagger_openapi_uri)
- [router.swagger.template_filename](/docs/reference/app-parameters.md#router_swagger_template_filename)
- [router.swagger.template_variables](/docs/reference/app-parameters.md#router_swagger_template_variables)

#### Descriptor Loader Parameters

- [router.descriptor_loader.cache](/docs/reference/app-parameters.md#router_descriptor_loader_cache)
- [router.descriptor_loader.resources](/docs/reference/app-parameters.md#router_descriptor_loader_resources)

#### Error Handling Middleware Parameters

- [router.error_handling_middleware.codec_context](/docs/reference/app-parameters.md#router_error_handling_middleware_codec_context)
- [router.error_handling_middleware.default_language](/docs/reference/app-parameters.md#router_error_handling_middleware_default_language)
- [router.error_handling_middleware.default_media_type](/docs/reference/app-parameters.md#router_error_handling_middleware_default_media_type)
- [router.error_handling_middleware.fatal_error_message](/docs/reference/app-parameters.md#router_error_handling_middleware_fatal_error_message)
- [router.error_handling_middleware.fatal_error_status_code](/docs/reference/app-parameters.md#router_error_handling_middleware_fatal_error_status_code)
- [router.error_handling_middleware.produced_languages](/docs/reference/app-parameters.md#router_error_handling_middleware_produced_languages)
- [router.error_handling_middleware.produced_media_types](/docs/reference/app-parameters.md#router_error_handling_middleware_produced_media_types)

#### Payload Decoding Middleware Parameters

- [router.payload_decoding_middleware.codec_context](/docs/reference/app-parameters.md#router_payload_decoding_middleware_codec_context)

#### String Trimming Middleware Parameters

- [router.string_trimming_middleware.trimmer](/docs/reference/app-parameters.md#router_string_trimming_middleware_trimmer)

#### Request Body Parameter Resolver Parameters

- [router.request_body_parameter_resolver.default_error_message](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_default_error_message)
- [router.request_body_parameter_resolver.default_error_status_code](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_default_error_status_code)
- [router.request_body_parameter_resolver.default_validation_enabled](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_default_validation_enabled)
- [router.request_body_parameter_resolver.hydrator_context](/docs/reference/app-parameters.md#router_request_body_parameter_resolver_hydrator_context)

#### Request Cookie Parameter Resolver Parameters

- [router.request_cookie_parameter_resolver.default_error_status_code](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_default_error_status_code)
- [router.request_cookie_parameter_resolver.default_error_message](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_default_error_message)
- [router.request_cookie_parameter_resolver.hydrator_context](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_hydrator_context)
- [router.request_cookie_parameter_resolver.default_validation_enabled](/docs/reference/app-parameters.md#router_request_cookie_parameter_resolver_default_validation_enabled)

#### Request Header Parameter Resolver Parameters

- [router.request_header_parameter_resolver.default_error_message](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_default_error_message)
- [router.request_header_parameter_resolver.default_error_status_code](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_default_error_status_code)
- [router.request_header_parameter_resolver.default_validation_enabled](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_default_validation_enabled)
- [router.request_header_parameter_resolver.hydrator_context](/docs/reference/app-parameters.md#router_request_header_parameter_resolver_hydrator_context)

#### Request Query Parameter Resolver Parameters

- [router.request_query_parameter_resolver.default_error_message](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_default_error_message)
- [router.request_query_parameter_resolver.default_error_status_code](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_default_error_status_code)
- [router.request_query_parameter_resolver.default_validation_enabled](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_default_validation_enabled)
- [router.request_query_parameter_resolver.hydrator_context](/docs/reference/app-parameters.md#router_request_query_parameter_resolver_hydrator_context)

#### Request Variable Parameter Resolver Parameters

- [router.request_variable_parameter_resolver.default_error_message](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_default_error_message)
- [router.request_variable_parameter_resolver.default_error_status_code](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_default_error_status_code)
- [router.request_variable_parameter_resolver.default_validation_enabled](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_default_validation_enabled)
- [router.request_variable_parameter_resolver.hydrator_context](/docs/reference/app-parameters.md#router_request_variable_parameter_resolver_hydrator_context)

#### Encodable Response Resolver Parameters

- [router.encodable_response_resolver.codec_context](/docs/reference/app-parameters.md#router_encodable_response_resolver_codec_context)
- [router.encodable_response_resolver.default_media_type](/docs/reference/app-parameters.md#router_encodable_response_resolver_default_media_type)
