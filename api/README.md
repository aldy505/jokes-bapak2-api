# Jokes Bapak2 API

Still work in progress

## Development

```bash
# Install modules
$ go mod download
# or
$ go mod vendor

# run the local server
$ go run main.go

# build everything
$ go build main.go
```

There is a placeholder data ready for you to query it manually in `/app/v1/platform/database/placeholder.sql`. Have a good time developing!

## Used packages

| Name | Version | Type |
| --- | --- | --- |
| [gofiber/fiber](https://github.com/gofiber/fiber) | `v2.14.0` | Framework |
| [jackc/pgx](https://github.com/jackc/pgx) | `v4.11.0` | Database |
| [go-redis/redis](https://github.com/go-redis/redis) | `v8.11.0` | Cache |
| [patrickmn/go-cache](https://github.com/patrickmn/go-cache) | `v2.1.0+incompatible` | Cache |
| [joho/godotenv](https://github.com/joho/godotenv) | `v1.3.0` | Config |
| [getsentry/sentry-go](https://github.com/getsentry/sentry-go) | `v0.11.0` | Logging |
| [aldy505/phc-crypto](https://github.com/aldy505/phc-crypto) | `v1.1.0` | Utils |
| [Masterminds/squirrel](https://github.com/Masterminds/squirrel ) | `v1.5.0` | Utils |
| [aldy505/bob](https://github.com/aldy505/bob) | `v0.0.1` | Utils |
| [gojek/heimdall](https://github.com/gojek/heimdall) | `v7.0.2` | Utils |
| [georgysavva/scany](https://github.com/georgysavva/scany) | `v0.2.9` | Utils |
| [stretchr/testify](https://github.com/stretchr/testify) | `v1.5.1` | Tests |

## Directory structure

```
.
├── app
│  └── v1
│     ├── app.go        - v1 application entry point
│     ├── core          - Pure business logic
│     ├── handler       - Route handler
│     ├── middleware    - App middleware handler
│     ├── models        - Output and input schema
│     ├── platform
│     │  ├── cache      - In-memory cache setup functions
│     │  └── database   - Database setup functions
│     ├── routes        - Routes definition & assignment
│     └── utils         - Utility functions
├── Dockerfile          - Docker image for API
├── go.mod              - Module information & dependencies
├── go.sum              - Packages lock file
├── main.go             - Application entry point
└── README.md           - You are here
```

## `.env` configuration

```ini
ENV=development
PORT=5000

DATABASE_URL=postgres://postgres:password@localhost:5432/jokesbapak2
REDIS_URL=redis://@localhost:6379

SENTRY_DSN=
```