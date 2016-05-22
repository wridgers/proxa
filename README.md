# Proxa

Proxa is a configurable HTTP reverse proxy.

It is still in development and should not be used in production.

## Install

    $ go get github.com/wridgers/proxa

## Example configuration

```json
{
  "frontend": {
    "bind": ":8080",
    "routes": [
      {"prefix": "/api/", "backend": "api"},
      {"prefix": "/", "backend": "default"}
    ]
  },

  "backends": [
    {
      "name":  "default",
      "addrs": ["localhost:8081", "localhost:8082"]
    },
    {
      "name": "api",
      "addrs": ["localhost:8090"]
    }
  ]
}
```
