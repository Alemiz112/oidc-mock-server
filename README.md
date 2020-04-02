# mock-oidc-user-server

| WARNING: DO NOT USE IN PRODUCTION |
| --------------------------------- |


A mock user server providing OpenID Connect (OIDC) flows for development and testing.

Uses the excellent [node-oidc-provider](https://github.com/panva/node-oidc-provider), which comes with dev interactions/flows out of the box (OIDC compliant). Any username and password combination is permitted for logging in, making this very useful for development and CI.

## Usage

Example usage via Docker Compose:

```yaml
version: '3.7'
services:
  mock_user_service:
    image: gridsuite/gridsuite-oidc-mock-server:v0.0.1
    environment:
      - PORT=9090
      - CLIENT_ID=my-client
      - CLIENT_SECRET=my-secret
      - CLIENT_REDIRECT_URI=http://localhost:8080/cb
      - CLIENT_LOGOUT_REDIRECT_URI=http://localhost:8080
    ports:
      - 9090:9090
```

## Dev

Prerequisites:

- NodeJS (v10.15.0+)
- Yarn

To install dependencies:

```shell
yarn install
```

To build the Docker image locally:

```shell
docker build -t gridsuite-oidc-mock-server .
```
