RabbitMQ dockerfile with init user and password from env vars, remove guest account.

## Usage
`docker-compose.yaml` Example:
```yaml
version: "3.3"
services:
  rabbit:
    image: THIS_IMAGE
    environment:
      RABBITMQ_USER: SOME_USER_NAME
      RABBITMQ_PASS_FILE: '/run/secrets/rabbit_pass'
    secrets:
      - rabbit_pass
      
secrets:
  rabbit_pass:
    file: "SOME_PATH/rabbit_pass"
```