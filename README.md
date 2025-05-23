
```markdown
# URL Shortener Service

A fast and reliable URL shortening service built with Go, using Gin framework, GORM, and Redis for caching.

## Features

- URL shortening with unique codes
- Fast redirects to original URLs
- Redis caching for improved performance
- PostgreSQL database for persistent storage
- Environment-based configuration

## Tech Stack

- Go (Golang)
- Gin Web Framework
- GORM ORM
- Redis
- PostgreSQL

## Prerequisites

- Go 1.19 or higher
- PostgreSQL
- Redis
- Docker (optional)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd url-shortener
```

2. Create a `.env` file:
```bash
# Database configuration
DB_HOST=db
DB_USER=
DB_PASSWORD=
DB_NAME=
DB_PORT=5432
DB_SSLMODE=disable
DB_TIMEZONE=Asia/Shanghai

# Application configuration
PORT=8080
ENDPOINT=http://short.softlife.reggeerr.com/
GIN_MODE=release

# Redis configuration
REDIS_HOST=cache
REDIS_PORT=6379
```

3. Install dependencies:
```bash
go mod download
```

4. Run the application:
```bash
go run main.go
```

## API Endpoints

### Shorten URL
```
POST /url/shorten

Request:
{
    "orignal_url": "https://example.com/very-long-url"
}

Response:
{
    "short_url": "http://localhost:8080/abc123"
}
```

### Redirect
```
GET /:shortCode
```

## Usage Example

```bash
# Create short URL
curl -X POST http://localhost:8080/url/shorten \
  -H "Content-Type: application/json" \
  -d '{"orignal_url":"https://example.com/very-long-url"}'

# Access shortened URL
curl -L http://localhost:8080/abc123
```

## License



MIT License

## Author

Racheal777 - kuranchieracheal@gmail.com

```