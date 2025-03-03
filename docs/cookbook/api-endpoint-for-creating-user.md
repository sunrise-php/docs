# API Endpoint for Creating a User

First and foremost, this is a demonstration example, so it does not include storage logic—it merely sets the direction for getting started.

## DTO

First, let's define a DTO that will reflect the data structure expected from the client.

```php
declare(strict_types=1);

namespace App\Dto\User;

final readonly class CreateUserRequest
{
    public function __construct(
        #[\SensitiveParameter]
        public string $email,
        #[\SensitiveParameter]
        public string $password,
    ) {
    }
}
```

## Controller

Now, let's create a controller and define an action for user creation.

> Check out the [controller annotation reference](/docs/reference/controller-annotations.md) to better understand what's happening here.

```php
declare(strict_types=1);

namespace App\Controller\Api;

use App\Dictionary\MediaType;
use App\Dto\User\CreateUserRequest;
use Sunrise\Http\Router\Annotation\Consumes;
use Sunrise\Http\Router\Annotation\PostApiRoute;
use Sunrise\Http\Router\Annotation\RequestBody;

final readonly class UserController
{
    #[PostApiRoute('api.users.create', '/api/users')]
    #[Consumes(MediaType::JSON)]
    public function createUser(
        #[RequestBody] CreateUserRequest $createUserRequest,
    ): void {
    }
}
```

## cURL

Nothing else is required, let's test the ready endpoint using the `cURL` CLI utility.

```bash
curl -i -X POST -H 'Content-Type: application/json' -d '{"email":"foo@example.com","password":"P@$$w0rD"}' http://localhost:8000/api/users
```

```text
HTTP/1.1 204 No Content
Host: localhost:8000
Date: Fri, 21 Feb 2025 03:46:17 GMT
Connection: close
X-Powered-By: PHP/8.4.3

```

## Swagger

Now we can finalize the work by updating Swagger.

```bash
php bin/app router:openapi:build-document
```

The updated Swagger should look something like the screenshot below.

![Screenshot](media/api-endpoint-for-creating-user-swagger-screenshot.png)
